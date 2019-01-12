HttpHeaders模块
```
设置Http报文的头标。

: expires       24h;
: expires       0;
: expires       -1;
: expires       epoch;
: add_header    Cache-Control private;

增加头标
    add_header name value
    当HTTP应答状态码为200，204，301，302，或304时，增加指定的HTTP头标。
    头标的值可以使用变量

expires
    expires [time|epoch|max|off]
    使用本指令可以控制HTTP应答中的expires和Cache-Control的头标（起到控制页面缓存的作用）
    time使用正数或负数。”Expires“头标的值将通过当前系统时间加上您设定的time值来获得。
        epoch
    指定expires值为1 January，1970，00：00：01 GMT
        max
    指定expires值为31 December 2037 23：59：59 GMT，Cache-Control的值为10年。
        -1
    指定Expires值为服务器当前时间 -1s，即永远过期。
    Cache-Control头标的值由您指定的时间来决定：
       负数： Cache-Control：no-cache
        整数或零：Cache-Control：max-age=#
                #指定时间的秒数。
    off表示不修改Expires和Cache-Control的值。
    
    
    
```