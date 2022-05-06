# rabbitmq

### 开启图形化管理界面

```
1:进入容器内部
docker exec -it rabbitmq /bin/bash
2:进入rabbitmq的可执行命令目录
cd /opt/rabbitmq/sbin
3:图形化界面默认是关闭的，这里需要开启
./rabbitmq-plugins enable rabbitmq_management
```

### 控制台页面：

```
之后可以通过Ip:15672端口访问图形化界面，
默认账号：admin
默认密码：admin
```



