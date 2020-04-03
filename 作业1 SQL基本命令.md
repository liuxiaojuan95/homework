### 一、介绍对数据库操作相关的命令
#### 1.创建一个新的数据库

**命令**

```sql
	create database student_3;   
```

**结果**


#### 2.查看和选择数据库

**命令**
```sql
       show databases;
       use student_3;
```

**结果**


#### 3.删除数据库

**命令**
```sql
      drop student_3;
```

**结果**


### 二、如何查看MySQL数据库中的存储引擎
#### 1.查看所支持的存储引擎

**命令**
```sql
       show engines;
```

**结果**


#### 2.查看默认的存储引擎

**命令**
```sql
      show variables like '%storage_engine%';
```

**结果**


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


#### 2.查看表的定义信息

**命令**
```sql
     describe tsc;
     show create table tsc;
```

**结果**


#### 3.删除表

**命令**
```sql
      drop table tsc;
      describe tsc;
```

**结果**


#### 4.修改表名

**命令**
```sql
      alter table tsc rename tsc1;
      show tables from student_3;
```

**结果**


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


##### 2）在表的最前面增加字段

**命令**
```sql
     desc tsc1;
     alter table tsc1
         add tel varchar(45) first;
     desc tsc1;
```
 
 **结果**
 
 
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


##### 4）删除字段

**命令**
```sql
   desc  tsc1;   
      alter table tsc1
         drop loc varchar(40);
   desc  tsc1;
```

**结果**


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


##### 2）同时修改字段的名字和数据类型

**命令**
```sql
    desc  tsc1;
    alter table tsc1
      change tel Tel varchar(40);
    desc  tsc1;
```

**结果**


##### 3）修改字段的顺序

**命令**
```sql
     desc  tsc1;
     alter table tsc1
         modify id int(11) after name;
     desc  tsc1;
```

**结果**


### 四、操作表的约束

**命令**
```sql
      create table tsc2(
 	deptno int not null,  # 设置非空约束(NOT NULL,NK)
	dname VARCHAR(20) default 'Petter', # 设置字段的默认值(DEFAULT)
	); 
```

**结果**


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


#### 2.同时插入多条数据记录

**命令**
```sql
      insert into tsc1(Tel,name,id brith,addr)
                 values(54322,'zhanzhan',02,0805,'henan'),
		       (54323,'bobo',03,1006,'chongqing');
      select * from table tsc1;
```

**结果**


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
 ```
 
 **结果**
 
 
