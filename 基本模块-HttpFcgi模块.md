HttpFcgi模块
```
允许Nginx与FastCGI进行交互，并通过传递参数来控制FastCGI进程工作。

    location / {
        fastcgi_pass localhost:9000;
        fastcgi_index index.php;

        fastcgi_param SCRIPT_FILENAME /home/www/scripts/php$fastcgi_script_name;
        fastcgi_param QUERY_STRING $query_string;
        fastcgi_param REQUEST_METHOD $request_method;
        fastcgi_param CONTENT_TYPE $content_type;
        fastcgi_param CONTENT_LENGTH $content_length;
    }

fastcgi_buffers
    fastcgi_buffers the_number is_size
    该指令集设置缓冲区的数量和大小，用于缓存从FastCGI Server接收到的数据。
    默认，一个缓冲区大小相当于一个页面的大小。根据平台不同设置为4k/8k;

fastcgin_buffer_size

fastcgi_cache
    fastcgi_cache zone
    设置缓存在共享内存中的名称，一块区域可以被用于不用的地方。

fastcgi_cache_key
    fastcgi_cache_key line
    设置缓存的key
        fastcgi_cache_key localhost:9000 $ request_uri

fastcgi_cache_methods
    fastcgi_cache_methods POST

fastcgi_cache_min_uses
    fastcgi_cache_min_uses n

fastcgi_cache_path

fastcgi_cache_use_stale

fastcgi_cache_valid

fastcgi_index

fastcgi_hide_header

fastcgi_ignore_client_abort
    用来决定忽略用户取消的请求。

fastcgi_innntercept_errors
    决定是否要把客户端转向4xx和5xx错误页，或允许nginx自动指定错误页。
    需要明确错误页，才有用。

fastcgin_param
   fastcgin_param parameter value
   指定的参数，将被传递给FastCGI-server
   


```