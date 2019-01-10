Charset模块
```
该模块用来添加文本编码类型到HTTP应答头”Content-Type indicated“
还能将服务器端网页原来的文本编码转换成另一种文本编码，输出给客户端。

override_charset on | off
    该指令开启时，如果后端的FASTCGI服务器响应头带有Content-type头信息，将开启编码转换。

charset

charset_map

source_charset

```