HttpIndex模块
```
实现在轮询和客户端IP之间的后端服务器负荷平衡

    upstream backend{
        server backend1.example.com weight=5;
        server backend2.example.com:8000;
        server unix:/tmp/backend3;
    }
    server{
        location /{
            proxy_pass http://backend;
        }
    }

ip_hash

    upstream backend{
        ip_hash;
        server backend1.example.com;
        server backend2.example.com;
        server backend3.example.com down;
        server backend4.example.com;
    }

server

```