HttpAutoindex模块
```
此模块用于自动生成目录列表。
ngx_http_autoindex_module只在ngx_http_index_module模块未找到索引文件时发生请求。
    location /{
        : autoindex on;
    }
    
autoindex
    on|off
    激活、关闭自动索引

autoindex_exact_size
    on|off
    设定索引时文件大小的单位。

autoindex_localtime
    on|off
    开启以本地时间来显示文件时间的功能。默认为关

```