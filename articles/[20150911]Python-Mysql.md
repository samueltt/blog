
```
sudo pip install mysql-python
```
这个时候有可能安装不上,出现一个报错

```
mysql_config: not found
```
这个错误是,我们一般安装mysql的时候,没有安装开发库

```
sudo apt-get install libmysqlclient-dev
```
安装开发库之后,再执行安装

```
sudo pip install mysql-python
```
测试代码

```
#!/usr/bin/env python
#-- encoding:utf-8 --

import MySQLdb
 
try:
    conn=MySQLdb.connect(host='localhost',user='root',passwd='root',db='yourdbname',port=3306)
    cur=conn.cursor()
    cur.execute('select * from test')
    cur.close()
    conn.close()
except MySQLdb.Error,e:
    print "Mysql Error %d: %s" % (e.args[0], e.args[1])

```
