HttpLimit Zone
```
针对条件，进行会话的并发连接数控制。

http {
    : limit_zone    one     $binary_remote_addr   10m;

    : ...

    : server{
        : ...

        :location /download/{
            : limit_conn one 1;
        }
    }
}

limit_zone
    limit_zone zone_name $variable the_size
    定义了一个数据区，里面记录会话状态信息
    $variable定义判断会话的变量；
    the_size定义记录区的总容量；

limit_conn
    limit_conn zone_name the_size
    一个会话最大的并发连接数。
    超过指定的并发连接数，服务器返回”Service unavailable"(503)

        limit_zone one $binary_remote_addr 10m;
        : server{
            : location /download/{
                : limit_conn one 1;
            }
        }
    

```