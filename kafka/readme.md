# kafka



## 创建topic的两种方式：

### 方法一(修改topicname)

```

bin/kafka-topics.sh --create --topic topicname --replication-factor 1 --partitions 1 --zookeeper localhost:2181
```



#### 方法二

```
conf/server.properties开启自动创建配置：auto.create.topics.enable=true
```



使用：

https://blog.csdn.net/qq_21040559/article/details/122839376







### 终端

```
#进入kafka容器
docker exec -it kafka01 /bin/bash
#进入kafka 命令行
cd /opt/kafka_2.13-2.8.1/bin/
#开启生产者
kafka-console-producer.sh  --broker-list 192.168.3.109:9092 --topic TestComposeTopic

![在这里插入图片描述](https://img-blog.csdnimg.cn/82fead6065ca4480a55ac7dce7d13483.png#pic_center)

```



### 终端2

```
#进入kafka容器
exec -it kafka01 /bin/bash
#进入kafka 命令行
cd /opt/kafka_2.13-2.8.1/bin/
#开启消费者
kafka-console-consumer.sh --bootstrap-server 192.168.3.109:9092 --topic TestComposeTopic --from-beginning
![在这里插入图片描述](https://img-blog.csdnimg.cn/0d80cd76bc9e4e458c29fc541a203cb7.png#pic_center)

```

