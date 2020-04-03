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
       use database student_3;
```

**结果**


#### 3.删除数据库

**命令**
```sql
      drop database student_3;
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
     use database student_3;
     create table tsc（
     id int(11),
     name VARCHAR(45),
     brith DATETIME
     );
```

**结果**


#### 2.查看表的定义信息

**命令**
```sql
     describe table tsc;
     show create table tsc;
```

**结果**


#### 3.删除表

**命令**
```sql
      drop table tsc;
      describe table tsc;
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
     desc table tsc1;
     alter table tsc1
         add addr varchar(45);
     desc table tsc1;
```

**结果**


##### 2）在表的最前面增加字段

**命令**
```sql
     desc table tsc1;
     alter table tsc1
         add tel varchar(45) first;
     desc table tsc1;
```
 
 **结果**
 
 
##### 3）在表指定字段后增加字段

**命令**
```sql
     desc table tsc1;
     alter table tsc1
         add loc varchar(40) 
	      after tel varchar(45);
     desc table tsc1;
```

**结果**


##### 4）删除字段

**命令**
```sql
   desc table tsc1;   
      alter table tsc1
         drop loc varchar(40) ;
   desc table tsc1;
```

**结果**


#### 6.修改字段
##### 1）修改字段的数据类型

**命令**
```sql
    desc table tsc1;
    alter table tsc1
       modify tel int;
    desc table tsc1;
```

**结果**


##### 2）同时修改字段的名字和数据类型

**命令**
```sql
    desc table tsc1;
    alter table tsc1
      change tel Tel varchar(40);
    desc table tsc1;
```

**结果**


##### 3）修改字段的顺序

**命令**
```sql
     desc table tsc1;
     alter table tsc1
         modify id int(11) after name VARCHAR(45);
     desc table tsc1;
```

**结果**


### 四、操作表的约束

**命令**
```sql
      create table tsc2(
 	deptno int not null,  # 设置非空约束(NOT NULL,NK)
	name VARCHAR(20) default 'Petter', # 设置字段的默认值(DEFAULT)
	xname VARCHAR(20) unique,	#设置委员约束（UNIQUE,UK）
	loc VARCHAR(40)， 
	number int primary key auto_increment	#设置字段自动增加
	); 
```

**结果**


### 五、数据的操作
#### 1.插入数据记录

**命令**
```sql
      desc table tsc1;
      insert into tsc1(       )
                  vales(      );
      insert into tsc1(       )
                  vales(      );
select * from table tsc1;
```

**结果**


#### 2.同时插入多条数据记录

**命令**
```sql
      insert into tsc1(       )
                  vales(      ),
		       (      ),
		       (      );
      select * from table tsc1;
```

**结果**


#### 3.将一个表的记录插入另一个表中

**命令**
```sql
      
