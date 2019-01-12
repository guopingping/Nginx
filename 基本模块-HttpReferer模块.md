HttpRefer模块
```
当浏览器向web服务器发送请求的时候，一般会带上Referer，告诉服务器我是从哪个页面链接过来的。
服务器借此获得一些信息用于处理，如防盗链。因为Http referer头信息是可以通过程序来伪装生成的，
所以通过referer防盗链并非100%可靠。
    location /photos/ {
        valid_referers none blocked www.mydomain.com mydomain.com;

        if($invalid_referer){
            return 403;
        }
    }

```