# EX 3 SubQueries, Views and Joins 


## Create employee Table
```sql
CREATE TABLE EMP (EMPNO NUMBER(4) PRIMARY KEY,ENAME VARCHAR2(10),JOB VARCHAR2(9),MGR NUMBER(4),HIREDATE DATE,SAL NUMBER(7,2),COMM NUMBER(7,2),DEPTNO NUMBER(2));
```
## Insert the values
```sql
INSERT INTO EMP (EMPNO, ENAME, JOB, MGR, HIREDATE, SAL, COMM, DEPTNO)
VALUES (7369, 'jivan', 'CLERK', 7902, '17-DEC-80', 800, NULL, 20);

INSERT INTO EMP (EMPNO, ENAME, JOB, MGR, HIREDATE, SAL, COMM, DEPTNO)
VALUES (7499, 'karthi', 'SALESMAN', 7698, '20-FEB-81', 1600, 300, 30);

INSERT INTO EMP (EMPNO, ENAME, JOB, MGR, HIREDATE, SAL, COMM, DEPTNO)
VALUES (7521, 'rathish', 'SALESMAN', 7698, '22-FEB-81', 1250, 500, 30);

INSERT INTO EMP (EMPNO, ENAME, JOB, MGR, HIREDATE, SAL, COMM, DEPTNO)
VALUES (7566, 'faizal', 'MANAGER', 7839, '02-APR-81', 2975, NULL, 20);

INSERT INTO EMP (EMPNO, ENAME, JOB, MGR, HIREDATE, SAL, COMM, DEPTNO)
VALUES (7654, 'sriram', 'SALESMAN', 7698, '28-SEP-81', 1250, 1400, 30);

INSERT INTO EMP (EMPNO, ENAME, JOB, MGR, HIREDATE, SAL, COMM, DEPTNO)
VALUES (7698, 'augus', 'MANAGER', 7839, '01-MAY-81', 2850, NULL, 30);
INSERT INTO EMP (EMPNO, ENAME, JOB, MGR, HIREDATE, SAL, COMM, DEPTNO)
VALUES (7782, 'bla bla', 'MANAGER', 7839, '09-JUN-81', 2450, NULL, 10);

INSERT INTO EMP (EMPNO, ENAME, JOB, MGR, HIREDATE, SAL, COMM, DEPTNO)
VALUES (7788, 'cha cha', 'ANALYST', 7566, '19-APR-87', 3000, NULL, 20);

INSERT INTO EMP (EMPNO, ENAME, JOB, MGR, HIREDATE, SAL, COMM, DEPTNO)
VALUES (7839, 'KING', 'PRESIDENT', NULL, '17-NOV-81', 5000, NULL, 10);

INSERT INTO EMP (EMPNO, ENAME, JOB, MGR, HIREDATE, SAL, COMM, DEPTNO)
VALUES (7844, 'TURNER', 'SALESMAN', 7698, '08-SEP-81', 1500, 0, 30);

INSERT INTO EMP (EMPNO, ENAME, JOB, MGR, HIREDATE, SAL, COMM, DEPTNO)
VALUES (7876, 'ADAMS', 'CLERK', 7788, '23-MAY-87', 1100, NULL, 20);

INSERT INTO EMP (EMPNO, ENAME, JOB, MGR, HIREDATE, SAL, COMM, DEPTNO)
VALUES (7900, 'JAMES', 'CLERK', 7698, '03-DEC-81', 950, NULL, 30);
```

## Create department table
```sql
CREATE TABLE DEPT (DEPTNO NUMBER(2) PRIMARY KEY,DNAME VARCHAR2(14),LOC VARCHAR2(13));
```
## Insert the values in the department table
```sql
INSERT INTO DEPT (DEPTNO, DNAME, LOC) VALUES (10, 'ACCOUNTING', 'NEW YORK');

INSERT INTO DEPT (DEPTNO, DNAME, LOC) VALUES (20, 'RESEARCH', 'DALLAS');

INSERT INTO DEPT (DEPTNO, DNAME, LOC) VALUES (30, 'SALES', 'CHICAGO');

INSERT INTO DEPT (DEPTNO, DNAME, LOC) VALUES (40, 'OPERATIONS', 'BOSTON');
```

### Q1) List the name of the employees whose salary is greater than that of employee with empno 7566.


### QUERY:

![Screenshot 2023-10-10 152012](https://github.com/rathishc12/EX-3-SubQueries-Views-and-Joins/assets/120539398/7500931c-602d-4340-a1ec-b888a1d679a1)

### OUTPUT:
![Screenshot 2023-10-10 152029](https://github.com/rathishc12/EX-3-SubQueries-Views-and-Joins/assets/120539398/c9e1a29c-8da2-4062-a9b7-6391d8456628)

### Q2) List the ename,job,sal of the employee who get minimum salary in the company.

### QUERY:

![Screenshot 2023-10-10 152158](https://github.com/rathishc12/EX-3-SubQueries-Views-and-Joins/assets/120539398/b499241a-4214-43f5-8934-d4e870914cd9)

### OUTPUT:
![Screenshot 2023-10-10 152203](https://github.com/rathishc12/EX-3-SubQueries-Views-and-Joins/assets/120539398/b49f4e84-1fa0-4a63-a50b-28b774e6fcdf)

### Q3) List ename, job of the employees who work in deptno 10 and his/her job is any one of the job in the department ‘SALES’.

### QUERY:

![Screenshot 2023-10-10 152354](https://github.com/rathishc12/EX-3-SubQueries-Views-and-Joins/assets/120539398/3e140189-884b-46f1-95ab-b3cf4b18f57e)

### OUTPUT:

![Screenshot 2023-10-10 152358](https://github.com/rathishc12/EX-3-SubQueries-Views-and-Joins/assets/120539398/33cd5fb5-cef7-4860-8196-9b7f530f0882)

### Q4) Create a view empv5 (for the table emp) that contains empno, ename, job of the employees who work in dept 10.

### QUERY:

![Screenshot 2023-10-10 152532](https://github.com/rathishc12/EX-3-SubQueries-Views-and-Joins/assets/120539398/d3106cf7-380e-4bee-9b12-1886256287da)

### OUTPUT:
![Screenshot 2023-10-10 152613](https://github.com/rathishc12/EX-3-SubQueries-Views-and-Joins/assets/120539398/c8ab7ee4-b734-4852-b725-f51525c37725)

### Q5) Create a view with column aliases empv30 that contains empno, ename, sal of the employees who work in dept 30. Also display the contents of the view.

### QUERY:
```
CREATE VIEW emv30 AS SELECT empno AS "Employee Number",ename AS "Employee Nmae",sal AS "Salary" from em WHERE deptno = 30;
SELECT * FROM emv30;
```

### OUTPUT:
![Screenshot 2023-10-10 153047](https://github.com/rathishc12/EX-3-SubQueries-Views-and-Joins/assets/120539398/5c302d0e-c293-414d-8d53-923a0be1b28a)

### Q6) Update the view empv5 by increasing 10% salary of the employees who work as ‘CLERK’. Also confirm the modifications in emp table

### QUERY:
```
UPDATE emv5 SET sal = al * 1.1 WHERE job = 'CLERK';
```

### OUTPUT:
![image](https://github.com/rathishc12/EX-3-SubQueries-Views-and-Joins/assets/120539398/4545c411-8879-4522-ba05-90a6b7aa0bb7)

## Create a Customer1 Table
```sql
CREATE TABLE Customer1 (customer_id INT,cust_name VARCHAR(20),city VARCHAR(20),grade INT,salesman_id INT);
```
## Inserting Values to the Table
```sql
INSERT INTO Customer1 (customer_id, cust_name, city, grade, salesman_id) VALUES(3002, 'Nick ', 'New York', 100, 5001);
INSERT INTO Customer1 (customer_id, cust_name, city, grade, salesman_id) VALUES(3007, 'Brad ', 'New York', 200, 5001);
INSERT INTO Customer1 (customer_id, cust_name, city, grade, salesman_id) VALUES(3005, 'Graham', 'California', 200, 5002);
INSERT INTO Customer1 (customer_id, cust_name, city, grade, salesman_id) VALUES(3008, 'Julian', 'London', 300, 5002);
INSERT INTO Customer1 (customer_id, cust_name, city, grade, salesman_id) VALUES(3004, 'Johnson', 'Paris', 300, 5006);
INSERT INTO Customer1 (customer_id, cust_name, city, grade, salesman_id) VALUES(3009, 'Geameron', 'Berlin', 100, 5003);
INSERT INTO Customer1 (customer_id, cust_name, city, grade, salesman_id) VALUES(3003, 'Jotidor', 'Moscow', 200, 5007);
INSERT INTO Customer1 (customer_id, cust_name, city, grade, salesman_id) VALUES(3001, 'Brauzan', 'London', NULL, 5005);
```
## Create a Salesperson1 table
```sql
CREATE TABLE Salesman1 (salesman_id INT,name VARCHAR(20),city VARCHAR(20),commission DECIMAL(4,2));
```
## Inserting Values to the Table
```sql
INSERT INTO Salesman1 (salesman_id, name, city, commission) VALUES(5001, 'Jame', 'York', 0.15);
INSERT INTO Salesman1 (salesman_id, name, city, commission) VALUES(5002, 'Nainite', 'Paris', 0.13);
INSERT INTO Salesman1 (salesman_id, name, city, commission) VALUES(5005, 'Pilex', 'London', 0.11);
INSERT INTO Salesman1 (salesman_id, name, city, commission) VALUES(5006, 'Mcyon', 'Paris', 0.14);
INSERT INTO Salesman1 (salesman_id, name, city, commission) VALUES(5007, 'Paudam', 'Rome', 0.13);
INSERT INTO Salesman1 (salesman_id, name, city, commission) VALUES(5003, 'Lauen', 'San Jose', 0.12);
```
### Q7) Write a SQL query to find the salesperson and customer who reside in the same city. Return Salesman, cust_name and city.

### QUERY:
```
SELECT salesman1.name AS "Salesman",customer1.cust_name AS "Customer Name",sales1.city AS "City" from salesman1 INNER JOIN customer1 ON salesman1.city = customer.city;
```


### OUTPUT:
![Screenshot 2023-10-10 155056](https://github.com/rathishc12/EX-3-SubQueries-Views-and-Joins/assets/120539398/e9aedf5c-8f0c-4c14-adca-5987f7994bce)

### Q8) Write a SQL query to find salespeople who received commissions of more than 13 percent from the company. Return Customer Name, customer city, Salesman, commission.


### QUERY:
```
SELECT customer1.cust_name AS "Customer Name",customer1.city AS "Customer City",salesman1.name AS "Salesman",salesman1.commission AS "Commission" FROM salesman1 INNER JOIN customer1 ON salesman.salesman_id = customer1.salesman_id WHERE salesman1.commission  > 0.13;
```


### OUTPUT:

![Screenshot 2023-10-10 155133](https://github.com/rathishc12/EX-3-SubQueries-Views-and-Joins/assets/120539398/d91f913b-dcbd-4c83-8c31-86ae3f78fe6e)

### Q9) Perform Natural join on both tables

### QUERY:
```
SELECT customer1.cust_name AS "Customer Name",customer1.city AS "Customer City",salesman1.name AS "Salesman",salesman1.commission AS "Commission" FROM salesman1 INNER JOIN customer1 ON salesman.salesman_id = customer1.salesman_id WHERE salesman1.commission  > 0.13;
```


### OUTPUT:
![Screenshot 2023-10-10 155133](https://github.com/rathishc12/EX-3-SubQueries-Views-and-Joins/assets/120539398/d91f913b-dcbd-4c83-8c31-86ae3f78fe6e)
![Screenshot 2023-10-10 155505](https://github.com/rathishc12/EX-3-SubQueries-Views-and-Joins/assets/120539398/cb18c14b-05a4-4a4d-b469-e56a875c1780)

### Q10) Perform Left and right join on both tables

### QUERY:
### LEFT JOIN
```
SELECT * FROM salesman1 LEFT JOIN customer1 ON salesman1.salesman_id = customer1.salesman_id;
```

### OUTPUT:
![Screenshot 2023-10-10 155555](https://github.com/rathishc12/EX-3-SubQueries-Views-and-Joins/assets/120539398/581018d1-bdaa-475b-b732-b67c87b7ea98)

### RIGHT JOIN
```
SELECT * FROM salesman1 RIGHT JOIN customer1 ON salesman1.salesman_id = customer1.salesman_id;
```
### OUTPUT
![Screenshot 2023-10-10 155631](https://github.com/rathishc12/EX-3-SubQueries-Views-and-Joins/assets/120539398/f8b54981-b978-4ba6-8887-881133c092ca)

### RESULT:
Hence successfully created SubQueries, Views and Joins.


