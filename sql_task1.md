# Task01 打卡

## 1.1

编写一条 CREATE TABLE 语句，用来创建一个包含表 1-A 中所列各项的表 Addressbook （地址簿），并为 regist_no （注册编号）列设置主键约束

表1-A 表 Addressbook （地址簿）中的列

![Z4El4zKbbWnaVHro](.\image\71f46b1e1a52c6504af2f7845d78971d5b47e971.png)

#### sql

```sql
use shop;
create table Addressbook(
regist_no int not null,
name varchar(128) not null,
address varchar(256) not null,
tel_no char(10),
mail_address char(20),
primary key (regist_no));
```

## 1.2

假设在创建练习1.1中的 Addressbook 表时忘记添加如下一列 postal_code （邮政编码）了，请把此列添加到 Addressbook 表中。

列名 ： postal_code

数据类型 ：定长字符串类型（长度为 8）

约束 ：不能为 NULL

#### sql

```sql
alter table Addressbook add column postal_code char(8) not null;
```

## 1.3

编写 SQL 语句来删除 Addressbook 表。

## 1.4

编写 SQL 语句来恢复删除掉的 Addressbook 表。

#### 解决方案

在日常生活中我们时常会误删文件，我们通常的解决办法就是备份，以便于恢复误删的文件。数据库也一样，在删除前我们先备份一下数据。这里介绍一下在MySQL Workbench中的数据备份与恢复，在右边菜单栏里有导出这一项，我们可以通过导出来备份我们的数据库到指定文件夹

![image-20201214150518677](.\image\image-20201214150407188.png)

然后当我们删除表后，就可以导入刚刚备份的数据来恢复。

```sql
drop table Addressbook;
```

![image-20201214150733503](.\image\image-20201214150733503.png)
