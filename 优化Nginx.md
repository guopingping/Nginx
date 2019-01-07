优化Nginx

```
Nginx使用hash表来协助完成请求的快速处理；
考虑到保存键值的hash表存储单元的大小不至于超出设定参数，在启动和每次重新配置时，Nginx为hash表选择
尽可能小的尺寸。
直到hash表超过参数（hash max size）的大小才重新进行选择。

事件模型
    select - 标准方法 使用配置参数
            --with-select_module/--without-select_module
            启用或禁用这个模块
    poll - 标准方法
            --with-poll_module/--without-poll_modules
    kqueue - 高效的方法，使用与FreeBSD4.1+,OpenBSD2.9+,NetBSD2.0,MacOS X，使用双处理器的MacOS X系统使用kqueue可能会造成内核崩溃。
    epoll - 高效的方法，使用与Linux内核2.6版本及以后系统
    rtsig - 可执行的实时信号 使用Linux内核版本2.2.19以后的系统。默认情况下整个系统中不能出现大于1024个POSIX
        实时（排队）信号。对于高负载的服务器是低效的，所以要调节内核参数
            /proc/sys/kernel/rtsig-max
        增加队列的大小。从Linux的内核版本2.6.6-mm2开始，这个参数就不再使用了，并且对于每个进程有一个独立的信号队列，这个队列的大小可以用RLIMIT_SIGPENDING参数调节，当这个队列过于拥塞，nginx就放弃它并且开始使用
            poll
        处理连接直到恢复正常
    /dev/poll - 高效的方法
    eventport - 高效的方法

```