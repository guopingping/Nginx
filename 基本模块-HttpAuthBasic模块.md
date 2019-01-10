HttpAuthBasic模块
```
使用用户名和密码基于HTTP基本认证方法来保护你的站点或其部分内容。
    location / {
        : auth_basic "Restricted";
        : auth_basic_user_file conf/htpasswd;
    }

指令
    
auth_basic
    auth_basic [text|off]
    用于http基本认证的测试名和密码。分配的参数用于认证领域。
    值”off“可以使其覆盖来自上层指令的继承性。

auth_basic_user_file
    该指令为某认证领域指定htpasswd文件名。
    文件格式类似下面的内容：
        用户名：密码
        用户名2：密码2：注释
        用户名3：密码3

        密码必须使用函数crypt(3)加密。你可以使用来自Apache的htpasswd工具来创建密码文件。
        


```