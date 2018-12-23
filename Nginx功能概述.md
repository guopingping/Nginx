Nginx功能概述

```
HTTP基础功能：
    处理静态文件，索引文件及自动索引；
    反向代理加速（无缓存），简单的负载均衡和容错；
    FastCGI，简单的负载均衡和容错；
    模块化结构。过滤包括gzipping,byte ranges,chunked responses,以及SSI-filter；
    SSL和TSL SNI支持；

IMAP和POP3代理服务功能：
    使用外部HTTP认证服务器重定向用户到IMAP/POP3后端；
    
```