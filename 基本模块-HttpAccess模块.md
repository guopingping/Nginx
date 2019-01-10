HttpAccess模块
```
简易的基于主机的访问控制。

ngx_http_access_module  模块使有可能对特定IP客户端进行控制。规则检查按照第一次匹配的顺序

    location /{
        : deny 192.168.1.1;
        : allow 192.168.1.0/24;
        : allown 10.1.1.0/16;
        : deny all;
    }
    仅允许网段10.1.1.0/16和192.168.1.0/24中除192.168.1.1之外的ip访问。

放行
    allow [address|CIDR|all]

禁止
    deny [address|CIDR|all]

```