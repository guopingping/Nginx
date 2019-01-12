Memcached
```
进行简单的缓存以提高系统效率。

server {
    : location /{
        : set $memcached_key        $uri;
        : memcached_pass            name:11211;
        : default_type              text/html;
        : error_page                404=/fallback;
    }
    : location =/fallback{
        : proxy_pass            backend;
    }
}

memcached_pass [name:port]

memcached_connect_timeout [time]

memcached_read_timeout [time]

memcached_send_timeout [time]

memcached_buffer_size [size]

memcached_next_upstream [error|timeout|invalid_response|not_found|off]
```