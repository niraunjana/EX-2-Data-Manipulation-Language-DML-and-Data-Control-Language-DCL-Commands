# EX 2 Data Manipulation Language (DML) Commands and built in functions in SQL

## Date:
## AIM:
To create a manager database and execute DML queries using SQL.


## DML(Data Manipulation Language)
<div align="justify">
The SQL commands that deal with the manipulation of data present in the database belong to DML or Data Manipulation Language and this includes most of the SQL statements. It is the component of the SQL statement that controls access to data and to the database. Basically, DCL statements are grouped with DML statements.
</div>

## List of DML commands: 
<div align="justify">
INSERT: It is used to insert data into a table.<br>
UPDATE: It is used to update existing data within a table.<br>
DELETE: It is used to delete records from a database table.<br>
</div>

## Create the table as given below:
```sql
create table manager(enumber number(6),ename char(15),salary number(5),commission number(4),annualsalary number(7),Hiredate date,designation char(10),deptno number(2),reporting char(10));
```
## insert the following values into the table
```sql
insert into manager values(7369,'Dharsan',2500,500,30000,'30-June-81','clerk',10,'John');
insert into manager values(7839,'Subu',3000,400,36000,'1-Jul-82','manager',null,'James');
insert into manager values(7934,'Aadhi',3500,300,42000,'1-May-82','manager',30,NULL);
insert into manager values(7788,'Vikash',4000,0,48000,'12-Aug-82','clerk',50,'Bond');
```

### Q1) Update all the records of manager table by increasing 10% of their salary as bonus.

### QUERY:

update manager set salary=salary+(salary*0.10);


### OUTPUT:
![WhatsApp Image 2023-09-29 at 20 37 42](https://github.com/niraunjana/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119395610/1c7de1a4-6b7b-41cc-8241-5b889229a4dc)


### Q2) Delete the records from manager table where the salary less than 2750.


### QUERY:

delete from manager where salary<2750;


### OUTPUT:

![WhatsApp Image 2023-09-29 at 20 38 18](https://github.com/niraunjana/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119395610/3baa2c06-8284-45f2-bd2c-88b437b94cab)


### Q3) Display each name of the employee as “Name” and annual salary as “Annual Salary” (Note: Salary in emp table is the monthly salary)


### QUERY:

select ename as "Name",salary*12 as "Annual salary" from manager;


### OUTPUT:

![WhatsApp Image 2023-09-29 at 20 38 46](https://github.com/niraunjana/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119395610/dc07f99c-3dde-4559-af37-d1f2fcbe2836)


### Q4)	List the names of Clerks from emp table.


### QUERY:

select ename from manager where designation='clerk';

### OUTPUT:

![WhatsApp Image 2023-09-29 at 20 39 16](https://github.com/niraunjana/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119395610/f124bdd3-7e7f-4504-8473-13ba481dc26c)



### Q5)	List the names of employee who are not Managers.


### QUERY:

select ename from manager where designation <> 'manager';


### OUTPUT:

![WhatsApp Image 2023-09-29 at 20 40 22](https://github.com/niraunjana/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119395610/47346bb4-2b0e-4968-b067-144461fe5ef4)



### Q6)	List the names of employees not eligible for commission.


### QUERY:

select ename from manager where commission=0;


### OUTPUT:

![WhatsApp Image 2023-09-29 at 20 41 39](https://github.com/niraunjana/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119395610/8654b0c5-b271-4753-83a7-0ecf28a95efa)


### Q7)	List employees whose name either start or end with ‘s’.


### QUERY:

select ename from manager where ename like '%s' or ename like '%s';

### OUTPUT:

![WhatsApp Image 2023-09-29 at 20 42 07](https://github.com/niraunjana/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119395610/43ed4097-5514-4660-a1a3-a0f7d9095b7a)



### Q8) Sort emp table in ascending order by hire-date and list ename, job, deptno and hire-date.


### QUERY:

select ename,designation as "job",deptno,hierdate from manager order by hierdate asc;


### OUTPUT:

![WhatsApp Image 2023-09-29 at 20 42 45](https://github.com/niraunjana/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119395610/4eaa279a-6e6d-40d3-aed1-b9805a7d7389)


### Q9) List the Details of Employees who have joined before 30 Sept 81.


### QUERY:

select * from manager where designation hierdate<to_date('1981-09-30','YYYY-MM-DD');

### OUTPUT:

![WhatsApp Image 2023-09-29 at 20 43 12](https://github.com/niraunjana/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119395610/ab4b6679-e6ce-4be4-bd4d-9666e7e05e8e)



### Q10)	List ename, deptno and sal after sorting emp table in ascending order by deptno and then descending order by sal.


### QUERY:

select ename,deptno,salary from manager order by deptno asc,salary desc;


### OUTPUT:

![WhatsApp Image 2023-09-29 at 20 43 33](https://github.com/niraunjana/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119395610/ebf24176-dd05-46ef-8de2-36828fd201f6)


### Q11) List the names of employees not belonging to dept no 30,40 & 10


### QUERY:

select ename from manager where deptno not in (30,40,10);

### OUTPUT:

![WhatsApp Image 2023-09-29 at 20 43 59](https://github.com/niraunjana/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119395610/19938a36-1be8-4de2-be4a-eb836a8bb7bb)


### Q12) Find number of rows in the table EMP

### QUERY:

select count(*) from manager;

### OUTPUT:

![WhatsApp Image 2023-09-29 at 20 44 23](https://github.com/niraunjana/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119395610/9538bf7c-0a03-4942-a82a-106b8e69bbbf)



### Q13) Find maximum, minimum and average salary in EMP table.

### QUERY:
### MAXIMUM :

select max(salary) from manager;

### OUTPUT:

![WhatsApp Image 2023-09-29 at 20 44 50](https://github.com/niraunjana/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119395610/79969fb2-5c38-4ea7-9dbd-7b279efcf6b4)

### MINIMUM :

select min(salary) from manager;

### OUTPUT :

![WhatsApp Image 2023-09-29 at 20 45 20](https://github.com/niraunjana/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119395610/1eab398c-92cc-41b9-9b62-87109b85da16)


### AVERAGE :

select avg(salary) from manager;

### OUTPUT :

![WhatsApp Image 2023-09-29 at 20 45 46](https://github.com/niraunjana/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119395610/69083fa0-1fb9-4397-85bb-08369908ed40)



### Q14) List the jobs and number of employees in each job. The result should be in the descending order of the number of employees.

### QUERY:

SELECT designation AS job, COUNT(*) AS num_employees FROM manager GROUP BY designation ORDER BY num_employees DESC;

### OUTPUT:

![WhatsApp Image 2023-09-29 at 20 46 12](https://github.com/niraunjana/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119395610/3438da94-923a-48df-94b8-070987bda8da)

### RESULT :

To create a manager database and execute DML queries using SQL is executed successfully.
