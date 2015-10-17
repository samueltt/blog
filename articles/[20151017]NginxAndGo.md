简单版本：
```
location / {
  proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
  proxy_set_header Host $http_host;
  proxy_redirect off;
  proxy_pass http://localhost:8080;
}
```
一般静态文件由 nginx 提供，所以可以这样写
```
root /home/demo/goproj/src/Test/public;
try_files $uri/index.html $uri.html $uri @goapp;

location @goapp {
  proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
  proxy_set_header Host $http_host;
  proxy_redirect off;
  proxy_pass http://localhost:8080;
}
```