HttpProxy模块
```
用于转发请求到其他的服务器。
keep-alive是指在Http/1.1协议中，同一个连接中发出和接收多次Http请求，节省了创建TCP连接过程的时间开销。
而Http/1.0协议不具备keep-alive请求的能力。
在Http/1.0协议中，每一个到后端的请求都会创建一个连接，传输完成后悔删除这个连接。
Nginx采用Http/1.1协议与浏览器进行通信，采用http/1.0协议与后端服务器进行通信。

    location /{
        : proxy_pass        http://localhost:8000;
        : proxy_set_header  X-Real-IP   $remote_addr;
    }
    在使用Http proxy模块时，用户的整个请求会在nginx中缓冲直至传递给后端被代理的服务器。

proxy_buffer_size
    设置缓冲区大小，从被代理的后端服务器取得的响应内容，会先读取放置到这里。

proxy_buffering
    开启从后端被代理服务器的响应内容缓冲

proxy_cache
proxy_cache_path
paroxy_cache_methods
proxy_cache_min_uses
proxy_cache_valid
proxy_cache_use_stale

```