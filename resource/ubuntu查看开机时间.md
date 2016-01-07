```
date -d "$(awk -F. '{print $1}' /proc/uptime) second ago" +"%Y-%m-%d %H:%M:%S"
```
```
$ cat /proc/uptime
31351.83  31341.94
#第一个数字代表已经运行的时间

#可以用date命令来计算出系统的启动时间
$ date -d "$(awk -F. '{print $1}' /proc/uptime) second ago" +"%Y-%m-%d %H:%M:%S"

2011-03-17 00:50:51

#使用date命令计算系统的运行时间
$ cat /proc/uptime| awk -F. '{run_days=$1 / 86400;run_hour=($1 % 86400)/3600;run_minute=($1 % 3600)/60;run_second=$1 % 60;printf("系统已运行：%d天%d时%d分%d秒\n",run_days,run_hour,run_minute,run_second)}'
系统已运行：0天8时45分27秒
```
