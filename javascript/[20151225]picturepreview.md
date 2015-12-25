http://www.cnblogs.com/rubylouvre/p/4597344.html


本地图片预览
IE中的本地图片预览（以本地文件的形式访问）

在IE中能够很方便的实现本地网页的图片预览，IE中的<input type="file" id="file_upload">中的File对象中的value属性，存储的是要上传的文件的完整路径，在IE中只需要将这个完整路径作为一个Image对象的src属性，就能实现在这个Image对象中对这个上传的图片进行预览。

在IE中有如下方式:

var url;
var fileobj = document.getElementById(sourceId);
fileobj.select();
url = document.selection.createRange().text;
或者

var url = document.getElementById(sourceId).value;
两种方式获取到的路径直接给img src 可以进行本地图片的预览（可以加上file:///协议，效果一样），这两种方式对IE7、8、9、10、11下有效。

Firefox和Chrome的本地图片预览

在Firefox和Chrome中使用如下方式:

var url = window.URL.createObjectURL(document.getElementById(sourceId).files[0])
将得到的值给img src 进行图片预览。可能还会看到如下的方式：var url = obj.files.item(0).getAsDataURL();
这种使用Firefox File对象的getAsDataURL的方式，已经在Firefox 7.0以后弃用，Firefox DOM File，可能原因是在HTML5标准中有相关的定义。

