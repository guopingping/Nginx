HttpUserId
```
相当于Apache的mod_uid模块，主要用于做客户端的身份标识，
它主要使用$uid_got和$uid_set变量。

userid              on;
userid_name         uid;

userid_domain       example.com;
userid_path         /;
userid_expires      365d;
userid_p3p          'policyref="/w3c/p3p.xml",CP="CUR ADM OUR NOR STA NID"';


```