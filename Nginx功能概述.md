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
    使用外部HTTP认证服务器认证用户连接重定向用户后连接重定向到内部的SMTP后端；
    认证方法：
        POP3
        IMAP；
        SMTP；
        SSL支持；
        在IMAP和POP3模式下的STARTTLS和STLS支持；
    
支持的操作系统：

结构与扩展：
    一个主进程和多个工作进程。工作进程是单线程的，且不需要特殊授权即可运行；
    。。。
    最小化的数据拷贝操作；

其他HTTP功能：
    基于IP和名称的虚拟主机服务；
    Memcached的GET接口；
    支持keep-alive和管道连接；
    灵活简单的配置；
    重新配置和在线升级而无须中断客户的工作进程；
    可定制的访问日志，日志写入缓存，及快捷的日志回卷；
    4xx-5xx的错误代码的重定向；
    基于PCRE的rewrite重写模块；
    基于客户端IP地址和HTTP基本认证的访问控制；
    PUT、DELETE、MKCOL方法；
    支持FLV；
    带宽限制；

实验特性：
    内嵌的
        perl
    通过
        aio_read()   aio_write()
    的套接字工作的试验模块，仅在FreeBSD下。
    对线程的实验化支持，FreeBSD 4.x的实现基于rfork()

```