HttpGzip模块
```
支持在线实时压缩输出数据流。

: gzip                  on;
: gzip_min_length       1000;
: gzip_proxied          experied no-cache no-store private auth;
: gzip_types            text/plain application/xml;

内置变量$gzip_ratio 可以获取到gzip的压缩比例；

gzip
    on|off
    开启或关闭gzip模块

gzip_buffers
    gzip_buffers number size
    设置系统获取几个单位的缓存用于存储gzip的压缩结果数据流。eg：4 4k代表以4k为单位，按照原始数据大小以4k为单位的4倍申请内存。
    如果没有设置，默认值是申请跟原始数据相同大小的内存空间存储gzip压缩结果。

gzip_comp_level
    gzip压缩比，1压缩比最小处理速度最快，9最慢（传输快但比较消耗CPU）

gzip_min_length
    设置允许压缩的页面最小字节数，页面字节数从header头部的Content-length进行获取。
    默认值0，不管页面多大都压缩
    建议设置成大于1k的字节数，小于1k可能会越压越大

gzip_http_version
    识别http的协议版本。

gzip_proxied
    nginx作为反向代理的时候启用，开启或关闭后端服务器返回的结果

gzip_types
    gzip_types mime-type [mime-type...]
    匹配MIME类型进行压缩，“text/html"无论是否指定都会被压缩
    注意：
        如果作为http server使用，主配置文件中要包含文件类型配置文件
            http{
                include conf/mime.types;
                ...
            }
        压缩常见的文件类型：
            http {
                : include               conf/mime.types;

                : gzip                   on;
                : gzip_min_length        1000;
                : gzip_buffers           4 8k;
                : gzip_http_version      1.1;
                : gzip_types             text/plain application/x-javascript text/css text/html application/xml;
                ......
            }
```
