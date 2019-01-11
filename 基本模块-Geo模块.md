Geo模块
```
    geo模块用于做全局负载均衡，可以根据不同的客户端ip访问到不同的服务器。
    一些针对不同地区的客户，使用不同的服务器去处理的请求，可以使用geo模块。
        geo $geo{
            default 0;
            127.0.0.1/32 2;
            192.168.1.0/24 1;
            10.1.0.0/16 1;
        }

        geo $country {
            default         no;
            include         conf/geo.conf;
            127.0.0.0/24    us;
            127.0.0.1/32    ru;
            10.1.0.0/16     ru;
            192.168.1.0/24  uk;
        }
        
    default：任何ip地址，相当于0.0.0.0/0
    include：可以应用一个文本文件，里面包含geo的配置内容。

    geo
        geo $arg_remote_addr $geo {
            ...;
        }
```