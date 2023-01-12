# SQL Class

# DDL
1. It is use to modify the records insides the table.
2. It is not parmanent because dml is not directly connect to db.
3. If we want to save parmanent then we shoould make of tcl statement.

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
