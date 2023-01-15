# SQL Class
# Data Query Language (DQL)
It is used to read /retrive the data from database
It has only select command
We can retrive the data by useing.
1. Projection
2. Selection
3. Join

# Projection
It is the process to retrive the data by selecting coloumn is known as projection.
Syntax-: Select * /distinct coloumn-name expression / aliusing from table-name;
It has the two part of the order of execution.
1. From Clause
2. Select Clause

Note-:
1. Table /view does not exit- if the table is not present inside database we get this.
2. Invalid Identifier- if the coloumn name is wrong we get this.
3. No rows selected- if we does not have any record inside the table or if the given condition is not matched with any rows.

Q. WAQTD details of employee?
```
Select * from emp;
Select emp .* from emp;
```
Q. WAQTD all the details of dept?
```
Select * from dept;
```
Q. WAQTD details of salgrade?
```
Select * from salgrade;
```

# Distinct
It remove the duplicate.
Two distinct keywords cannot be used in one selecte statement.
Distinct can be applied to one or more coloumns.
Q. WAQTD the unique saleries from employee table?
```
Select distinct (Sal) from emp:
```
Q. WAQTD the unique mgr with deptno;
```
Select distinct mgr, deptno from emp;
```

# Expression
Combination of operands and operators.

Q. WAQTD all the details of the employee along with annual salery?
```
Select emp.*, sal*12 from emp;
```
Q. WAQTD employee name with half of salery?
```
Select name, sal*6 from emp;
```
# Aliasing
It is use to rename the table name and coloumn name.
We have three way to rename.
1. Useing as keyword between old-coloumn-name and new-coloumn-name.``` ename as empname; ```
2. Useing space between old-coloumn-name and new-coloumn-name.``` empno.eid; ```
3. Useing " " for new coloumn name.``` Sal "MONTHELY SALERY";```

Q. WAQTD the name of the employeee along with their salery as monthely salery?
```
Select ename,sal"Monthely Slery" from emp;
```
Q. WAQTD names of the employee sal& annualsal for all the employees?
```
Select ename,sal,sal*12 as annualsal from emp;
```
# Selection
The process of retriving the data by selecting both coloumn and rows is known as selection.
In this we have order of execution divide in three pars.
1. From Clause
2. Where Clause
3. Select Clause

Syntacx-: Select */distinct col-name expresssion / aliasing from table-name;
Note-:
Where clause is used to filter the records it execute row by row process.

Q. WAQTD all the details of employeee earning 3000?
```
Select * from emp where sal = 3000;
```
Q. WAQTD all the details who are working as MANAGER?
```
Select * from emp where job='MANAGER';
```
Q. WAQTD ename, job, sal, hiredate from employee who are working in deptno 30 ?
```
Select ename,job,sal,hiredate from emp where deptno = 30;
```
Q. WAQTD details of MARTIN ?
```
Select * from emp where ename = 'MARTIN';
```
Q. WAQTD details of the employeee whoe's reporting manager is 7756 ?
```
Select * from emp where mgr = 7756;
```
Q. WAQTD details of the employee   whoe's reporting manager is 7902 ? 
```
Select * from emp where empno = 7902;
```
Q. WAQTD all the details employee along with annualsal if annualsal is 9600 ?
```
Select emp.*, sal*12 annualsal where sal*12 = 9600;
```
# Operator
It is used to perform operation between operands and produce the result.
There are four type of operator.
1. Arithmatic Operator (+,-,/,*,%)
2. Relation or Compression operator (<,>,=,!=,=>,<=)
3. Logical Operator (AND,OR,NOT)
4. Special Operator (IS,IS NOT,IS NOT IN,LIKE,NOT LIKE,BETWEEN,NO BETWEEN)

## Arithmatic Operator
It is used to perform arithmatic operation on numberic values.

Q. WAQTD details of employee with 10% of like in there salery?
```
Select emp.*, sal*10 as like from emp;
```
Q. WAQTD details of employee along with deduction or 500 from the salery for all the employee?
```
Select emp.*, sal-500 as deduction from emp:
```
Q. WAQTD details of employee along with like 30% for their annual sal for all the employees?
```
Select emp.*,(sal*12)+(sal*30/100) from emp;
```


# Data Control Language (DCL)
It is  used to control access to data stored in a database between the user.
There is two part of DCL.
. Grant
. Revoke

# Grant 
1. It is a command or a staement which is used to given permission to the user.
2. Grant SQL statement on table name to user.
3. Syntax-: Grant select on emp to hr;

# Revoke
1. It is a command or a statement which is used to take back the given permission from the user.
2. Revoke sql statement on table name from user.
3. Syntax-: Revoke select on emp from hr;

# Data Defination Language (DDL)
1. It used to perform some Operation inside the Database.
2. It has direct connection to Database , so the changes are parmanent.

## Create
It used to create user or table structure.
1. creating user Syntax-: create user username identify by password;
```
create user u1 identified by lion;
Grant resource connect to u1;
```
2. creating table syntax-: create table tablename(col-n1 datatype(size) constraint,col-n2 datatype(size) constraint,col-n datatype(size) constraint,foreign key (col-name) reference parent-table-name(col-n));
```
create table hr(h-Id number(3) primary key,h-Name varchar(15));
```
```
create table Student(Id number(3) primary key,Name varchar(15),phoneno varchar(15),check (length(phoneno)=10),h-Id number(2) foreign key(h-Id),reference hr(h-Id));
```
## Drop
It used to delete the table, once the table is drop now the table present in recycle bin.
1.Drop syntax-: Drop table table-name;
```
Drop table e1;
```
In Drop there are two statement.
1. Flasback
2. Purge
### Flashback
It is used to restore the table if and only if it present in recycle bin.
1. Flashback Syntax-: flashback table tablename to before drop;
```
flashback table e1 to before drop;
```
### Purge
It is used to parmanentely delete the table if and only if the table in the recycle bin.
1. purge  Syntax-: Purge table tablename;
```
purge table e1;
```

## Truncate
It is used to delete the table record.
1. In use of truncate only record gets delete but table structure remain same.
2. We can not restore the record once we truncate the records.

3. Truncate Syntax-: Truncate table tableNmae;
```
truncate table e1;
```

## Rename
It used to rename old table name to new table name also renam the tablename.
1.Rename Syntax-: rename old-table-name to new-table-name;
```
rename e3 to emp3;
```

## Alter 
It use to perform 
1. add coloumn and drop coloumn.
2. rename coloumn name table name.
3. change the data type and size (datatype can be altered if the coloumn is empty).

### Add Coloumn 
Syntax-: alter table table-name add Coloumn-name datatype(size);
```
alter table e3 add email varchar(20);
```
### Drop Coloumn 
Syntax-: alter table table-name drop Coloumn Coloumn-name;
```
alter table e3 drop Coloumn ename;
```
### Rename Coloumn Name 
Syntax-: alter table table-name rename Coloumn old-Coloumn-name to new-coloumn-name;
```
alter table e3 rename Coloumn empno to eid;
```
### Rename table Name 
Syntax-: alter table old-table-name rename to new-table-name;
```
alter table e3 rename  emp3;
```
### Change Data Type and size 
Syntax-: alter table table-name modify coloumn-name datatype;
```
alter table emp3 modify email number(7,2);
```
### Note-: 1
If we forget to build a relation between two different table, it can be done later by useing alter
1. Syntax to add the coloumn which must be foreign key-: alter table table-name add coloumn-name datatype(size);
```
alter table emp3 add deptno number(2);
```
2. Syntax to add foreign key and refer the parent table.
```
alter table emp3 add foreign key(deptno) reference dept(deptno);
```
### Note-: 2
if we forgot the table whch is drop We can use ``` select * from recyclebin; ``` to  know the table name.
### Note-: 3
Once we drop the table the table structure will not be visible.


# Data Manipulation Language (DML)
1. It is use to modify the records insides the table.
2. It is not parmanent because dml is not directly connect to db.
3. If we want to save parmanent then we shoould make of TCL statement.

```
create table author(Id int(3) primary key,Name varchar(15),Profession varchar(15),Salery int(10),Dob varchar(10),Points varchar(10));
```

## Insert
It's used to insert the value into the table.
```
insert into author values(1,'Anupam','Struggler',1000,null,2);
insert into author values(2,'Aayush','Student',1000,null,20);
insert into author values(3,'Shalu','Developer',2500000,null,20);
insert into author values(4,'Diwakar','Farmer',10000,null,20);
insert into author values(5,'Uma','HouseWife',5000,null,20);
insert into author values(6,'Anoop','Developer',3500000,null,20);
```

## update
It is use to update the value into the table.
We can Swap the value if and only if the coloume have same data type.
```
update author set Dob=02102000 where Id=1;
update author set Dob=10041962 where Id=4;
update author set Dob=02101990 where Id=6;
update author set Dob=07051994 where Id=3;
update author set Dob=29042007 where Id=2;
update author set Name=Profession, Salery=Dob;
```

## Delete
It's used to delete the specific record or full table.
```
delete from author where Profession='Struggler';
delete from author;
```


# Transection cotrol Language(TCL)
1. It is used to save the traansection changes parmanentely, the transection can be insert, update, delete.
2. There are applicable only for DMl statements.
3. There are three stements are in TCL.
  . Commit
  . Rollback
  . Savepoint
## Commit
It helps us to save the transection parmanentely into the database.
Syntax-: Commit;
## Rollback
It is use to get the previous record upto save.
Syntax-: Rollback;
## Savepoint
Savepoint is used to restoration point.
Syntax-: Savepoint SavepointName;

```
insert into author values(1,'Uma','HouseWife',5000,null,20);
commit;
// if we commit then it save as parmanent
// 1 row created
insert into author values(2,'Uma','HouseWife',5000,null,20);
savepoint M;
// 2 row created
insert into author values(3,'Uma','HouseWife',5000,null,20);
insert into author values(4,'Uma','HouseWife',5000,null,20);
savepoint N;
//4 row created
insert into author values(5,'Uma','HouseWife',5000,null,20);
insert into author values(6,'Uma','HouseWife',5000,null,20);
insert into author values(7,'Uma','HouseWife',5000,null,20);
// 7 row created
rollback to O;
// 7 row created
rollback to N;
// 4 row created
rollback to M;
// 2 row created
rollback;
// empty the table
// 1 row created
```

