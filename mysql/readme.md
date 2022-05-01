# 更改用户远程连接

## 给予远程用户所有表所有权限

```sql
GRANT ALL ON *.* TO 'root'@'%';
```

## 更改加密规则

```sql
ALTER USER 'root'@'localhost' IDENTIFIED BY '123456' PASSWORD EXPIRE NEVER;
```

## 远程访问

```sql
ALTER USER 'root'@'%' IDENTIFIED WITH mysql_native_password BY '123456';
```

## 刷新权限

```sql
flush privileges;
```

