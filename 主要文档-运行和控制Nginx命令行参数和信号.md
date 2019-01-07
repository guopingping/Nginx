运行和控制Nginx命令行参数和信号

```
1、Nginx命令行参数
    -c </path/to/config> 为Nginx指定一个配置文件，来代替缺省的；
    -t 不运行，仅测试配置文件；
            nginx将检查配置文件语法的正确性，并尝试打开配置文件中所引用到的文件；
    -v nginx的版本；
    -V nginx的版本，编译器版本和配置参数；

2、nginx控制信号
    使用信号系统来控制主进程。
    默认，nginx将其主进程的pid写入到/usr/local/nginx/nginx.pid文件中。
    通过传递参数给./configure或使用pid指令，来改变该文件的位置；
    主进程可以处理以下的信号：
        TERM，INT：
                快速关闭
        QUIT：
                从容关闭；
        HUP：
                重载配置
                用新的配置开始新的工作进程
                从容关闭旧的工作进程
        USR1:
                重新打开日志文件
        USR2：
                平滑升级可执行程序
        WINCH：
                从容关闭工作进程

3、nginx启动、停止、重启命令
    nginx启动：
        sudo /usr/local/nginx/nginx
    nginx从容停止命令，等待所有请求结束后关闭服务：
        ps -ef |grep nginx
        kill -QUIT nginx 主进程号
    nginx快速停止命令，立刻关闭nginx进程：
        ps -ef |grep nginx
        kill -TERM nginx 主进程号
    强制停止：
        kill -9 nginx主进程号

    为pid命令设置的参数，用来存放nginx主进程号的文件：
        kill -信号类型(HUP|TERM|QUIT) cat /usr/local/nginx/nginx.pid

4、nginx重启命令
    简单型，先关闭进程，修改你的配置，重启进程。
        kill -QUIT cat /usr/local/nginx/nginx.pid
        sudo /usr/local/nginx/nginx
    重新加载配置文件，不重启进程，不会停止处理请求；
    平滑更新nginx二进制，不会体质处理请求；


```