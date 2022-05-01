

## 注意

都用默认需要准备至少4G的服务器





## 修改线程等配置优化：

GitLab 在部署完成启动之后，占用的内存会越来越大，默认情况的下配置文件（ /etc/gitlab/gitlab.rb）许多资源限定都是被注释的，此时可以通过手动开启，进行优化。

优化参数
### 减少进程数
```
unicorn['worker_processes'] = 2
```

### 减少数据库缓存
```
postgresql['shared_buffers'] = "256MB"
```

### 减少数据库并发数

```
postgresql['max_worker_processes'] = 8
```


### 注意
修改完成之后需要将配置重新加载，执行下面命令即可

```
gitlab-ctl reconfigure
gitlab-ctl restart
```





### 案例：

https://ouyangpeng.blog.csdn.net/article/details/84066417