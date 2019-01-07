
```
Nginx架构

    Nginx多进程模式
```
![Image Text](https://github.com/guopingping/Nginx/blob/master/image/chapter.PNG)

```
master来管理worker进程，所以只需要与master进程通信就可以了。
master进程会接收来自外界发来的信号，再根据信号做不同的事情。
要控制nginx，只需要通过kill向master进程发送信号就行了，从容重启nginx或重新加载配置，服务是不中断的。


好处：
    对于每个worker进程，都是独立的进程，不需要加锁，省掉了锁带来的开销，在编程及查找问题时，方便。
    采用独立的进程，可以让互相之间不会影响，一个进程结束，其他进程还在工作，服务不会中断，master会很快启动新的worker进程。
    worker进程异常退出，会导致当前worker上所有请求失败，不过不会影响到所有请求，降低了风险。

nginx采用了异步非阻塞的方式来处理请求，nginx可以同时处理成千上万的请求的。
不需要创建线程，每个请求占用的内存也很少，没有上下文切换，事件处理非常难的轻量级，循环处理多个准备好的事件。

nginx基础概念：
    connection
        在nginx中connection就是对tcp连接的封装，包括连接的socket，读事件，写事件。
    request
        处理请求，ngx_http_init_request
    keepalive
    pipe
    lingering_close
            


```

