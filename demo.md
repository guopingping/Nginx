Nginx
========================================================
nginx install
-------------------------------------------------------
```

https://www.cnblogs.com/meng1314-shuai/p/8335140.html
https://www.yiibai.com/nginx/beginners_guide.html

```

nginx配置
----------------------------------------------------------
```javascript
nginx.conf：

#user  nobody;
worker_processes  1;

#error_log  logs/error.log;
#error_log  logs/error.log  notice;
#error_log  logs/error.log  info;

#pid        logs/nginx.pid;


events {
    worker_connections  1024;
}

http {
    include       mime.types;
    default_type  application/octet-stream;

#     #log_format  main  '$remote_addr - $remote_user [$time_local] "$request" '
#     #                  '$status $body_bytes_sent "$http_referer" '
#     #                  '"$http_user_agent" "$http_x_forwarded_for"';

#     #access_log  logs/access.log  main;

#     sendfile        on;
#     #tcp_nopush     on;

#     #keepalive_timeout  0;
#     keepalive_timeout  65;

#     #gzip  on;

      server {
        listen       80;
        server_name  域名;
        
        #charset koi8-r;
        #access_log  logs/host.access.log  main;
        location /member {
            proxy_pass http://127.0.0.1:4021;
            proxy_set_header Host      $host;
    			  proxy_set_header X-Real-IP $remote_addr;
            proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
         }
        location /group1 {
            proxy_pass 代理地址;
        }
        #error_page  404              /404.html;
        # redirect server error pages to the static page /50x.html
        #
        error_page   500 502 503 504  /50x.html;
        location = /50x.html {
            root   html;
        }
    }

#     server {
#         listen       8080;
#         server_name  localhost;

#         #charset koi8-r;

#         #access_log  logs/host.access.log  main;

#         location / {
#             root   html;
#             index  index.html index.htm;
#         }

#         #error_page  404              /404.html;

#         # redirect server error pages to the static page /50x.html
#         #
#         error_page   500 502 503 504  /50x.html;
#         location = /50x.html {
#             root   html;
#         }

#         # proxy the PHP scripts to Apache listening on 127.0.0.1:80
#         #
#         #location ~ \.php$ {
#         #    proxy_pass   http://127.0.0.1;
#         #}

#         # pass the PHP scripts to FastCGI server listening on 127.0.0.1:9000
#         #
#         #location ~ \.php$ {
#         #    root           html;
#         #    fastcgi_pass   127.0.0.1:9000;
#         #    fastcgi_index  index.php;
#         #    fastcgi_param  SCRIPT_FILENAME  /scripts$fastcgi_script_name;
#         #    include        fastcgi_params;
#         #}

#         # deny access to .htaccess files, if Apache's document root
#         # concurs with nginx's one
#         #
#         #location ~ /\.ht {
#         #    deny  all;
#         #}
#     }


#     # another virtual host using mix of IP-, name-, and port-based configuration
#     #
#     #server {
#     #    listen       8000;
#     #    listen       somename:8080;
#     #    server_name  somename  alias  another.alias;

#     #    location / {
#     #        root   html;
#     #        index  index.html index.htm;
#     #    }
#     #}


#     # HTTPS server
#     #
#     #server {
#     #    listen       443 ssl;
#     #    server_name  localhost;

#     #    ssl_certificate      cert.pem;
#     #    ssl_certificate_key  cert.key;

#     #    ssl_session_cache    shared:SSL:1m;
#     #    ssl_session_timeout  5m;

#     #    ssl_ciphers  HIGH:!aNULL:!MD5;
#     #    ssl_prefer_server_ciphers  on;

#     #    location / {
#     #        root   html;
#     #        index  index.html index.htm;
#     #    }
#     #}
#     include servers/*;
 }


```
nginx常用命令
---------------------------------------------------------
```
stop - 快速关闭服务quit - 正常关闭服务reload - 重新加载配置文件reopen - 重新打开日志文件

nginx：启动
nginx -s stop：快速关闭服务
nginx -s quit：正常关闭服务
nginx -s reload：重新加载配置文件
nginx -s reopen：重新打开日志文件

```
