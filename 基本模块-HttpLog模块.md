HttpLog模块
```
ngx_http_log_module

    log_format  gzip  '$remote_addr - $remote_user [$time_local]  '
    : '"$request" $status $bytes_sent '
    : '"$http_referer" "$http_user_agent" "$gzip_ratio"';
    access_log  /spool/logs/nginx-access.log  gzip  buffer=32k;

access_log
    该指令用于设置日志文件的路径,格式和缓冲区大小.
    使用"off"作为唯一参数,将不记录日志文件.
    如果没有指定日志格式,将默认采用"combined"格式.缓冲区的大小必须小于写人磁盘文件的原子记录大小.

log_format
    该指令用来描述日志格式.
    在日志的格式中,可以使用Nginx的大多数通用变量,以及一些仅在写日志时存在的变量.

```