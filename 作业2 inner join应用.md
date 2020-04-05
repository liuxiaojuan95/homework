### 输出我 我的老板 我的老板的老板的名字

**命令**
```sql
  create table temployee(
    	deptno INT NOT NULL,
	empno INT PRIMARY KEY,
	ename VARCHAR(20),
	job VARCHAR(20),
    	MGR INT,
	Hiredate Date,
	sal float,
	comm float
	);  
  insert into temployee (empno, ename, job, MGR, Hiredate, sal, comm, deptno)  
	VALUES (7369, "SMITH", "CLERK", 7902, "1981-03-12", 800.00, NULL, 20),
		(7499, "ALLEN", "SALESMAN", 7698, "1982-03-12", 1600, 300, 30),
		(7521, "WARD", "SALESMAN", 7698, "1838-03-12", 1250, 500, 30),
		(7566, "JONES", "MANAGER", 7839, "1981-03-12", 2975, NULL, 20),
		(7654, "MARTIN", "SALESMAN", 7698, "1981-01-12", 1250, 1400, 30),
		(7698, "BLAKE", "MANAGER", 7839, "1985-03-12", 2450, NULL, 10),
		(7788, "SCOTT", "ANALYST", 7566, "1981-03-12", 3000, NULL, 20),
		(7839, "KING", "PRESIDENT", NULL, "1981-03-12", 5000, NULL, 10),
		(7844, "TURNER", "SALESMAN", 7689, "1981-03-12", 1500, 0, 30),
		(7878, "ADAMS", "CLERK", 7788, "1981-03-12", 1100, NULL,20),
		(7900, "JAMES", "CLERK", 7698,"1981-03-12",  950, NULL, 30),
		(7902, "FORD", "ANALYST", 7566, "1981-03-12", 3000, NULL, 20),
		(7934, "MILLER", "CLERK", 7782, "1981-03-12", 1300, NULL, 10)
	;
   select * from temployee;
   
   select *			
   from (temployee t1 inner join temployee t2 on t1. mgr= t2.empno )  inner join temployee t3 
   on t2. mgr= t3.empno;

   select t1.ename My_name,t2.ename My_b_name ,t3.ename My_b_b_name 	
from (temployee t1 inner join temployee t2 on t1. mgr= t2.empno )  inner join temployee t3 
on t2. mgr= t3.empno; 
```

**结果**
![](https://github.com/liuxiaojuan95/homework/blob/master/images/2.2.png)
![](https://github.com/liuxiaojuan95/homework/blob/master/images/2.2x.png)
![](https://github.com/liuxiaojuan95/homework/blob/master/images/2.3.png)
