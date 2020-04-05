### 一、介绍对数据库操作相关的命令
#### 1.创建一个新的数据库

**命令**

```sql
	create database student_3;   
```

**结果**
![1](https://github.com/liuxiaojuan95/homework/blob/master/images/1.1.png)

#### 2.查看和选择数据库

**命令**
```sql
       show databases;
       use student_3;
```

**结果**
![2](https://github.com/liuxiaojuan95/homework/blob/master/images/1.2.png)

#### 3.删除数据库

**命令**
```sql
      drop student_3;
```

**结果**
![](https://github.com/liuxiaojuan95/homework/blob/master/images/1.3.png)

### 二、如何查看MySQL数据库中的存储引擎
#### 1.查看所支持的存储引擎

**命令**
```sql
       show engines;
```

**结果**
![3](https://github.com/liuxiaojuan95/homework/blob/master/images/1.4.png)

#### 2.查看默认的存储引擎

**命令**
```sql
      show variables like '%storage_engine%';
```

**结果**
![4](https://github.com/liuxiaojuan95/homework/blob/master/images/1.5.png)

### 三、介绍对表操作的相关命令
#### 1.在数据库中创建一个新的表

**命令**
```sql
     use student_3;
     create table tsc(
     id int(11),
     name VARCHAR(45),
     brith DATETIME
     );
```

**结果**
![](https://github.com/liuxiaojuan95/homework/blob/master/images/1.6.png)

#### 2.查看表的定义信息

**命令**
```sql
     describe tsc;
     show create table tsc;
```

**结果**
![](https://github.com/liuxiaojuan95/homework/blob/master/images/1.7.png)

#### 3.删除表

**命令**
```sql
      show tables from student_2;
      drop table tbsc;
      show tables from student_2;
```

**结果**
![](https://github.com/liuxiaojuan95/homework/blob/master/images/1.15.png)

#### 4.修改表名

**命令**
```sql
      alter table tsc rename tsc1;
      show tables from student_3;
```

**结果**
![](https://github.com/liuxiaojuan95/homework/blob/master/images/1.9.png)

#### 5.增加字段和删除字段
##### 1）在表的最后面增加字段

**命令**
```sql
     desc tsc1;
     alter table tsc1
         add addr varchar(45);
     desc tsc1;
```

**结果**
![](https://github.com/liuxiaojuan95/homework/blob/master/images/1.10.png)

##### 2）在表的最前面增加字段

**命令**
```sql
     desc tsc1;
     alter table tsc1
         add tel varchar(45) first;
     desc tsc1;
```
 
 **结果**
![](https://github.com/liuxiaojuan95/homework/blob/master/images/1.11.png) 
 
##### 3）在表指定字段后增加字段

**命令**
```sql
     desc  tsc1;
     alter table tsc1
         add loc varchar(40) 
	      after tel;
     desc tsc1;
```

**结果**
![](https://github.com/liuxiaojuan95/homework/blob/master/images/1.12.png)

##### 4）删除字段

**命令**
```sql
   desc  tsc1;   
      alter table tsc1
         drop loc varchar(40);
   desc  tsc1;
```

**结果**
![](https://github.com/liuxiaojuan95/homework/blob/master/images/1.13.png)

#### 6.修改字段
##### 1）修改字段的数据类型

**命令**
```sql
    desc  tsc1;
    alter table tsc1
       modify tel int;
    desc tsc1;
```

**结果**
![](https://github.com/liuxiaojuan95/homework/blob/master/images/1.14.png)

##### 2）同时修改字段的名字和数据类型

**命令**
```sql
    desc  tsc1;
    alter table tsc1
      change tel Tel varchar(40);
    desc  tsc1;
```

**结果**
![](https://github.com/liuxiaojuan95/homework/blob/master/images/1.16.png)

##### 3）修改字段的顺序

**命令**
```sql
     desc  tsc1;
     alter table tsc1
         modify id int(11) after name;
     desc  tsc1;
```

**结果**
![](https://github.com/liuxiaojuan95/homework/blob/master/images/1.17.png)

### 四、操作表的约束

**命令**
```sql
      create table tsc2(
 	deptno int not null,  # 设置非空约束(NOT NULL,NK)
	dname VARCHAR(20) default 'Petter', # 设置字段的默认值(DEFAULT)
	); 
```

**结果**
![](https://github.com/liuxiaojuan95/homework/blob/master/images/1.18.png)

### 五、数据的操作
#### 1.插入数据记录

**命令**
```sql
      desc  tsc1;
      insert into tsc1(Tel,name,id,brith,addr)
                  values(54321,'xingxing',01,0213,'hunan');
select * from table tsc1;
```

**结果**
![](https://github.com/liuxiaojuan95/homework/blob/master/images/1.19.png)

#### 2.同时插入多条数据记录

**命令**
```sql
      insert into tsc1(Tel,name,id brith,addr)
                 values(54322,'zhanzhan',02,0805,'henan'),
		       (54323,'bobo',03,1006,'chongqing');
      select * from table tsc1;
```

**结果**
![](https://github.com/liuxiaojuan95/homework/blob/master/images/1.20.png)

#### 3.将一个表的记录插入另一个表中

**命令**
```sql
      create table tsc3(
      tel varchar(40),
      name varchar(45),
      id int(11),
      brith datetime,
      addr varchar(45)
      );
      desc tsc3;
      insert into tsc3(tel,name,id,brith,addr)
      values(54324,'wangxiao',04,0905,'henan');
      select * from tsc3;
      insert into tsc1(Tel,name,id,brith,addr)
      select tel,name,id,brith,addr
      from tsc3;
      select * from tsc1;
 ```
 
 **结果**
![](https://github.com/liuxiaojuan95/homework/blob/master/images/1.21.1.png) 
![](https://github.com/liuxiaojuan95/homework/blob/master/images/1.21.2.png)
![](https://github.com/liuxiaojuan95/homework/blob/master/images/1.21.3.png)
