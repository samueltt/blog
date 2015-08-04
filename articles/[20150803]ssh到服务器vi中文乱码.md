遇到了同样的问题，主要是远程服务器的语言编码与终端的编码不一致。

在远程服务器端的 ~/.bashrc 文件里面加入以下代码：

   export LANG='UTC-8'
   export LC_ALL='en_US.UTF-8'

然后bash一下，中文就可以正常显示。

下次登录 .bashrc 文件自动运行，中文照样正常显示。
