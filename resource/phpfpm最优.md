```

max_children php-fpm最大可执行进程数
max_requests 每个进程请求多少次后就自动结束，然后重新建立一个children。
request_terminate_timeout 每个请求最长执行时间

max_children=40 , 每个children平均占用20M-30M内存，children越多，可以同时接受的并发数量越多，一般children的值是网站最高并发数+浮动值，这值再×内存占用，就是你需要用到的内存。
max_requests = N 是指当每个children接受了N次请求以后，就会把自己杀死，然后重新建立一个children。
PV / max_children = 每一个children接受的request次数
比如上面的值是1000，而你定义的是10240，那么fpm要超过10天才能杀死children并重建，这样如果存在内存泄露的话，就会导致进程占用过多的内存而无法释放，从而使fpm的处理能力降低，还会产生一些莫名其妙的错误。
但是如果你把这个值设置的过小，fpm频繁的杀死children并重建，也会导致额外的开销。
最好的优化当然是根据你网站的运行情况，去不断的调试，找到一个平衡点。
针对max_children还有一个偷懒的做法，如果你的php是5.3，那么你可以把fpm的style设置为apache-like，这个时候children的数量就由fpm自动控制。相应的配置参数是
start_servers：起始进程数量
min_spare_servers：最小进程数量
max_spare_servers：最大进程数量
当服务器比较空闲的时候，fpm会主动杀死一些多余的children，用来节约资源，当服务器繁忙的时候，服务器会自动建立更多的children。

php-fpm.conf有两个至关重要的参数：
一个是”max_children”,
另一个是”request_terminate_timeout”
我的两个设置的值一个是”40″，一个是”900″，但是这个值不是通用的，而是需要自己计算的。


计算的方式如下：
如果你的服务器性能足够好，且宽带资源足够充足，PHP脚本没有系循环或BUG的话你可以直接将”request_terminate_timeout” 设置成0s。0s的含义是让PHP-CGI一直执行下去而没有时间限制。而如果你做不到这一点，也就是说你的PHP-CGI可能出现某个BUG，或者你的 宽带不够充足或者其他的原因导致你的PHP-CGI能够假死那么就建议你给”request_terminate_timeout”赋一个值，这个值可以 根据你服务器的性能进行设定。一般来说性能越好你可以设置越高，20分钟-30分钟都可以。由于我的服务器PHP脚本需要长时间运行，有的可能会超过10 分钟因此我设置了900秒，这样不会导致PHP-CGI死掉而出现502 Bad gateway这个错误。

而”max_children”这个值又是怎么计算出来的呢？这个值原则上是越大越好，php-cgi的进程多了就会处理的很快，排队的请求就会很少。设 置”max_children”也需要根据服务器的性能进行设定，一般来说一台服务器正常情况下每一个php-cgi所耗费的内存在20M左右，因此我 的”max_children”我设置成40个，20M*40=800M也就是说在峰值的时候所有PHP-CGI所耗内存在800M以内，低于我的有效内 存1Gb。而如果我的”max_children”设置的较小，比如5-10个，那么php-cgi就会“很累”，处理速度也很慢，等待的时间也较长。如 果长时间没有得到处理的请求就会出现504 Gateway Time-out这个错误，而正在处理的很累的那几个php-cgi如果遇到了问题就会出现502 Bad gateway这个错误。


max_requests即是说每个进程若超过这个数目(跟php进程有一点点关系,关系不大),就自动杀死..我这里应该设置512的,不过懒得压力测 试了,设置大一点,不过也不要设置过大,是个结构体,没测试过,接近8K到9K大小.网上动辄设置100k,有点浪费内存了.一个进程浪费大小接近1M. 按照网上常用配置的128个进程,大概浪费100M左右.好吧,我承认100M是白菜价,但也别这样浪费..= =

max_children基本就是进程数,跟nginx的进程没有想象中的那么大,因为FPM会自己管理进程(有待考证,起码我简单浏览了一下源码,认为是这个意思).参数不宜设置过大,很占内存,进程的消耗就不用我多说了.

max_children较好的设置方式根据req/s来设置,若程序是 100 req/s的处理能力..最大并发是10K,那么就设置 100比较好,这是动态来调整的.

不过你若用php 5.3,也可以把style设置为apache-like,那么设置start_servers,min_spare_servers,max_spare_servers三个参数就可以自动调整
很简单,具体看配置文件,这样的设置之后,在高负载和复杂的php程序会省事一点,毕竟测试req/s是可恶的体力活. 
 
```
