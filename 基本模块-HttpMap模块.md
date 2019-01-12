map
```
    该模块允许分类，或映射一组值到一组不同的值，并将这些值存储在一个变量中。

        map $http_host $name {
            hostnames;

            default         0;
            example.com     1;
            *.example.com   1;
            test.com        2;
            *.test.com      2;
            .site.com       3;
        }

    map
        map $var1 $var2 {...}

    map_hash_max_size
        number

    map_hash_bucket_size
        n

    
```