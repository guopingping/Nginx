HttpSSI模块
```
SSI，服务器嵌入
工作原理：
    将内容发送到浏览器之前，可以使用“服务器端包含SSI”指令文本，图形或应用程序
信息包含到网页中。
处理服务器端包含文件SSI的处理。列表中的命令当前并未完全支持。

    location /{
        : ssi on;
    }

ssi
ssi_silent_errors
    在处理SSI文件出错时不输出错误提示
ssi_types
ssi_value_length
    定义ssi允许使用的参数长度

内置变量    
    ngx_http_ssi_module支持两种内置变量
        $date_local
            当前的本地时区时间，配置选项“timefmt”控制格式
        $date_gmt
            当前的GMT时间，配置选项“timefmt”控制格式
```