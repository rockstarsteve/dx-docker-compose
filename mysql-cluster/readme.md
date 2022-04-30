### 主库创建复制用户

1. CREATE USER 'woniu'@'%' IDENTIFIED WITH mysql_native_password BY 'woniu123456';
2.  
3. GRANT REPLICATION SLAVE ON *.* TO 'woniu'@'%';

### 查看 master 机器的状态

SHOW MASTER STATUS

### 从库设置 master 的信息

CHANGE MASTER TO
MASTER_HOST='172.0.0.5',
MASTER_USER='woniu',
MASTER_PASSWORD='woniu123456',
MASTER_LOG_FILE='mysql-bin.000003',
MASTER_LOG_POS=1163;

### 开始同步

1. 开始同步

   start slave;

2.   同步状态

   show slave status;