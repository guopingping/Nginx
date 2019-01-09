http核心模块

指令

```
alias
    alias file-path | directory-path
    default:no
    context:location
    用于url与文件系统路径之间实现映射。

    root
    localtion /i/{
        alias /spool/w3/images/;
    }
    eg：在示例中，访问url地址“/i/top.gif",会返回"/spool/w3/images/top.gif"

client_body_in_file_only
    client_body_in_file_only on|off
    允许将一个客户端的请求内容记录到一个文件中，该文件在请求完成后不会被删除。
    在内置perl中，该指令用于调试&r->request_body_file方法。

client_body_in_single_buffer
    指定是否保持整个内容在一个单一的客户端请求缓冲区中，该指令在使用变量$request_body时被推荐使用

client_body_buffer_size
    client_body_buffer_size 128k
    该指令指定客户端请求内容的缓冲区大小。如果客户端请求内容大于缓冲区中，整个请求内容或部分内容将被写入临时文件。
    缓冲区默认大小相当于网页大小的两倍，为8K或16K。

client_body_temp_path
    client_body_temp_path dir-path [level1][levels2][level3]
    该指令用于指定存放请求内容临时文件的目录，缓存目录最多支持3层子目录
    eg：client_body_temp_path /spool/nginx/client_temp 1 2

client_body_timeout
    client_body_timeout time
    设置读取客户端请求内容的超时时间，超过指令设置时间，Nginx返回“request time out”错误信息（http状态码408）

client_header_buffer_size
    client_header_buffer_size size
    设置客户端请求的header头缓冲区大小
    
client_header_timeout
    设置读取客户端请求Header头信息的超时时间，超过指令设置时间，Nginx返回“request time out”错误信息（http状态码408）

client_max_body_size
    设置允许接受的客户端请求内容的最大值，即客户端请求的Header头部信息中设置的Content-length的最大值。
    超过，Nginx返回“Request Entity Too Large”（http状态码413）。

default_type
    default_type MIME-type
    MIME-type：告诉浏览器请求的文件媒体类型

directio

error_page
    设置如果出现指定的http错误状态码，返回给客户端显示的对应url地址。

if_modified_since

index
    index file [file...]
    设置nginx默认首页文件

internal
    设置某个location路径只能在nginx内部使用，外部无法访问。

keepalive_timeout
    可使客户端到服务端的连接持续有效，当出现对服务器的后续请求时，可避免建立或重新建立连接。

keepalive_requests n
    设置keep-alive连接使用次数。
    一次请求结束后，如果该连接使用次数没有超过keepalive_requests指令设置的请求次数，服务器不会立即主动断开连接，
    直到达到keepalive_timeout指令设置的时间，才关闭连接。

large_client_header_buffers
    设置客户端请求的header头缓冲区大小，默认4kb
    不能超过设置的值，否则会报414或400错误
    如果客户端cookie信息较大，需增加缓冲区大小

limit_except
    限制http方法访问location中内容

limit_rate speed
    用来限速，单位：字节数/秒
    提供http下载等应用中会用到
    限速只对一个连接起效，如果客户端开启两个连接下载，下载的速度将是限速的两倍

limit_rate_after time
    设置一个字节数，下载的字节数大于该值后，limit_rate指令的限速功能起效。

listen
    设置虚拟主机监听的服务器地址和端口号
    如果只设置一个服务器名或ip地址，则默认端口号为80

location
    对不同的url进行不同的设置，可以使用字符串、正则表达式，需使用以下前缀：
        ~*：标识不区分大小写的匹配
        ~：标识分大小写的匹配

log_not_found on|off
    启用或禁用404错误日志，禁止nginx记录找不到robots.txt和favicon.ico这类文件的错误信息。

log_subrequest on|off
    启动或禁止access_log中记录类似rewrite rules,SSI request等请求

root
    指定请求的文档根目录





```