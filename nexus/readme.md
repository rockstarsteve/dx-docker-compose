

## 注意：

1. 由于要使用权限需要对data下的目录进行读写授权
2. nexus官方配置里默认是2703M的内存占用，而如果你机器只有2G的话那么是跑不起来的，但是修改下jvm启动参数还是可以做到运行起来的。





## 登录密码（或者查看控制台）

```
sudo docker exec -it nexus bash
cat /nexus-data/admin.password
```



