# EX 2 Data Manipulation Language (DML) Commands and built in functions in SQL
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
create table managers(enumber number(6),ename char(15),salary number(5),commission number(4),annualsalary number(7),Hiredate date,designation char(10),deptno number(2),reporting char(10));
```
## insert the following values into the table
```sql
insert into managers values(7369,'Dharsan',2500,500,30000,'30-June-81','clerk',10,'John');
insert into managers values(7839,'Subu',3000,400,36000,'1-Jul-82','manager',null,'James');
insert into managers values(7934,'Aadhi',3500,300,42000,'1-May-82','manager',30,NULL);
insert into managers values(7788,'Vikash',4000,0,48000,'12-Aug-82','clerk',50,'Bond');
```
### Output:
![Creating and inserting values into table](https://github.com/Jeevapriya14/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/121003043/d22ba1c6-fb6e-4716-8688-205c41f63df4)
### Q1) Update all the records of manager table by increasing 10% of their salary as bonus.
### QUERY:
```
update managers set salary=salary+(salary*10/100);
```
### OUTPUT:
![Updation](https://github.com/Jeevapriya14/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/121003043/16012ed2-b415-4c2d-8429-c5e962ee126b)
### Q2) Delete the records from manager table where the salary less than 2750.
### QUERY:
```
delete managers where salary<2750;
```
### OUTPUT:
![Deletion](https://github.com/Jeevapriya14/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/121003043/994dab65-e8d7-412d-9187-206821347524)
### Q3) Display each name of the employee as “Name” and annual salary as “Annual Salary” (Note: Salary in emp table is the monthly salary)
### QUERY:
```
SELECT
ename AS "Name",
salary*12 AS "Annual Salary"
FROM
managers;
```
### OUTPUT:
![Updation](https://github.com/Jeevapriya14/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/121003043/df079f1f-55a2-4455-b568-db441286b812)

### Q5)	List the names of Clerks from emp table.
### QUERY:
```
select ename from managers where designation='clerk';
```
### OUTPUT:
![Listing](https://github.com/Jeevapriya14/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/121003043/0a740ac9-e901-4224-818c-787564c43ad9)
### Q6)	List the names of employee who are not Managers.
### QUERY:
```
select ename from managers where designation!='manager';
```
### OUTPUT:
![Listing](https://github.com/Jeevapriya14/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/121003043/15c5d52f-61af-43e6-94b6-907767602779)
### Q7)	List the names of employees not eligible for commission.
### QUERY:
```
select ename from managers where commission=0;
```
### OUTPUT:

![Listing](https://github.com/Jeevapriya14/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/121003043/2de2e750-4b77-4a53-bf5f-b55b64ab3c21)
### Q8)	List employees whose name either start or end with ‘s’.
### QUERY:
```
select ename from managers where ename LIKE 'S%' OR ename LIKE '%S';
```
### OUTPUT:
![Listing](https://github.com/Jeevapriya14/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/121003043/b3fc0396-1bf9-4763-ae8b-31ae0b8236b9)
### Q9) Sort emp table in ascending order by hire-date and list ename, job, deptno and hire-date.
### QUERY:
```
select ename,designation,deptno,hiredate from managers order by hiredate ASC;
```
### OUTPUT:
![Sorting](https://github.com/Jeevapriya14/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/121003043/6e037653-4091-4059-a92a-bddd805eecda)
### Q10) List the Details of Employees who have joined before 30 Sept 81.
### QUERY:
```
select * from managers where hiredate < '30 SEP 81';
```
### OUTPUT:

![Listing](https://github.com/Jeevapriya14/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/121003043/91b5ae39-3447-49d6-8c33-24c2c1723493)
### Q11)	List ename, deptno and sal after sorting emp table in ascending order by deptno and then descending order by sal.
### QUERY:
```
select ename,deptno,salary from managers ORDER BY deptno ASC,salary desc;
```
### OUTPUT:

![Listing](https://github.com/Jeevapriya14/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/121003043/507318c9-f9ea-44ec-bcae-57a47c7bce5b)
### Q12) List the names of employees not belonging to dept no 30,40 & 10
### QUERY:
```
select ename from managers where deptno NOT IN (30,40,10);
```
### OUTPUT:
![Listing](https://github.com/Jeevapriya14/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/121003043/df10ee58-33c1-4859-957c-cbc5c676d9bf)
### Q13) Find number of rows in the table EMP
### QUERY:
```
select count(*) as rownumber from managers;
```
### OUTPUT:
![Count of rows](https://github.com/Jeevapriya14/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/121003043/25ab3941-ae65-4e15-9498-2a05af5e73e9)
### Q14) Find maximum, minimum and average salary in EMP table.
### QUERY:
```
select MAX(salary) as maximumsal,MIN(salary) as minimumsal,AVG(salary)
as averagesal from managers;
```
### OUTPUT:
![Finding](https://github.com/Jeevapriya14/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/121003043/8134d873-db9f-4a41-acfb-9e7b1cabaf5b)
### Q15) List the jobs and number of employees in each job. The result should be in the descending order of the number of employees.
### QUERY:
```
select designation,count(*) as number_employee from managers GROUP BY designation ORDER BY number_employee DESC;
```
### OUTPUT:
![image](https://github.com/harinidq/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/113497680/2043256a-0c3a-4975-bc2c-56f1a47ac955)



