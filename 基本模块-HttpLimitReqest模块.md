HttpLimitReqest模块
```
    允许你对Session会话，单个客户端IP地址，限制指定单位时间内的并发请求数，
    你可以在一定程度上减轻多应用服务器的DOS恶意攻击。

    http{
        limit_req_zone $binary_remote_addr zone=one:10m rate=1r/s;
        ...
        server{
            ...
            location /search/ {
                limit_req zone=one burst=5;
            }
        }
    }
```