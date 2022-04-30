# 给予远程用户所有表所有权限

GRANT ALL ON *.* TO 'root'@'%';

# 更改加密规则

ALTER USER 'root'@'localhost' IDENTIFIED BY '123456' PASSWORD EXPIRE NEVER;

# 远程访问

ALTER USER 'root'@'%' IDENTIFIED WITH mysql_native_password BY '123456';

# 刷新权限

flush privileges;





# 建议主从同步时候不要建同步的数据库！！！

### 1.查看 master 机器的状态

SHOW MASTER STATUS

### 2.从库设置 master 的信息

CHANGE MASTER TO
MASTER_HOST='127.0.0.1',
MASTER_PORT=3316,
MASTER_USER='root',
MASTER_PASSWORD='root',
MASTER_LOG_FILE='mysql-bin.000003',  # 从1中查看到的file的数据放这
MASTER_LOG_POS=1163;        # 从1中查看到的position的数据放这

### 3.开始同步

1. 开始同步

   start slave;

2.   同步状态

   show slave status;
   
3. 如果有错误

   1. 先停掉slave，然后跳过错误步数，再启动slave
      1. stop slave     
      2. set global [sql](https://www.jb51.cc/tag/sql/)_slave_skip_counter=1; 