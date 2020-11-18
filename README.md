### CREATE DATABASE
```sql
CREATE DATABASE COMPANY;
```

### EMPLOYEE TABLE
```sql
CREATE TABLE EMPLOYEE (
Fname varchar(255),
Minit varchar(255),
Lname varchar(255),
Ssn varchar(255) NOT NULL PRIMARY KEY,
Bdate date,
Address varchar(255),
Sex varchar(255),
Salary int,
Super_ssn varchar(255),
Dno int);


INSERT INTO employee (Fname, Minit, Lname, Ssn, Bdate, Address, Sex, Salary, Super_ssn, Dno)
VALUES ('John', 'B', 'Smith', '123456789', '1965-01-09', '731 Fondren, Houston, TX', 
'M', 30000, '333445555', 5),

('Franklin', 'T', 'Wong', '333445555', '1955-12-08', '638 Voss, Houston, TX', 
'M', 40000, '888665555', 5),

('Alicia', 'J', 'Zelaya', '999887777', '1968-01-19', '3321 Castle, Spring, TX', 
'F', 25000, '987654321', 4),

('Jennifer', 'S', 'Wallace', '987654321', '1941-06-20', '291 Berry, Bellaire, TX', 
'F', 43000, '888665555', 4),

('Ramesh', 'K', 'Narayan', '666884444', '1962-09-15', '975 Fire Oak, Humble, TX', 
'M', 38000, '333445555', 5),

('Joyce', 'A', 'English', '453453453', '1972-07-31', '5631 Rice, Houston, TX', 
'F', 25000, '333445555', 5),

('Ahmad', 'V', 'Jabbar', '987987987', '1969-03-29', '980 Dallas, Houston, TX', 
'M', 25000, '987654321', 4),

('James', 'E', 'Borg', '888665555', '1937-11-10', '450 Stone, Houston, TX', 
'M', 55000, NULL, 1);
```


### DEPARTMENT TABLE
```sql
CREATE TABLE DEPARTMENT (
Dname varchar(255),
Dnumber int NOT NULL PRIMARY KEY,
Mgr_ssn varchar(255),
Mgr_start_date date);

INSERT INTO DEPARTMENT (Dname, Dnumber, Mgr_ssn, Mgr_start_date)
VALUES ('Research', 5, '333445555', '1988-05-22'),
('Administration', 4, '987654321', '1995-01-01'),
('Headquarters', 1, '888665555', '1981-06-19')
```

### DEPT_LOCATIONS TABLE
```sql
CREATE TABLE DEPT_LOCATIONS (
Dnumber int NOT NULL,
Dlocation varchar(255) NOT NULL);

ALTER TABLE DEPT_LOCATIONS ADD CONSTRAINT PK_CUSTID PRIMARY KEY (Dnumber, Dlocation);

INSERT INTO DEPT_LOCATIONS (Dnumber, Dlocation)
VALUES 
( 1, 'Houston'),
( 4, 'Stafford'),
( 5, 'Bellaire'),
( 5, 'Sugarland'),
( 5, 'Houston')
```

###  PROJECT TABLE
```sql
CREATE TABLE PROJECT (
Pname varchar(255),
Pnumber int NOT NULL PRIMARY KEY,
Plocation varchar(255),
Dnum int);


INSERT INTO PROJECT (Pname, Pnumber, Plocation, Dnum)
VALUES 
( 'ProductX', 1, 'Bellaire', 5),
( 'ProductY', 2, 'Sugarland', 5),
( 'ProductZ', 3, 'Houston', 5),
( 'Computerization', 10, 'Stafford', 4),
( 'Reorganization', 20, 'Houston', 1),
( 'Newbenefits', 30, 'Stafford', 4)
```

### DEPENDENT TABLE
```sql
CREATE TABLE DEPENDENT (
Essn varchar(255) NOT NULL,
Dependent_name varchar(255) NOT NULL,
Sex varchar(255),
Bdate date,
Relationship varchar(255));

ALTER TABLE DEPENDENT ADD CONSTRAINT PK_CUSTID PRIMARY KEY (Essn, Dependent_name);

INSERT INTO DEPENDENT (Essn, Dependent_name, Sex, Bdate,Relationship)
VALUES 
( '333445555', 'Alice', 'F', '1986-04-05', 'Daughter'),
( '333445555', 'Theodore', 'M', '1983-10-25', 'Son'),
( '333445555', 'Joy', 'F', '1958-05-03', 'Spouse'),
( '987654321', 'Abner', 'M', '1942-02-28', 'Spouse'),
( '123456789', 'Michael', 'M', '1988-01-04', 'Son'),
( '123456789', 'Alice', 'F', '1988-12-30', 'Daughter'),
( '123456789', 'Elizabeth', 'F', '1967-05-05', 'Spouse')
```

### WORKS_ON TABLE
```sql
CREATE TABLE WORKS_ON (
Essn varchar(255) NOT NULL,
Pno int NOT NULL,
Hours varchar(255));

ALTER TABLE WORKS_ON ADD CONSTRAINT PK_CUSTID PRIMARY KEY (Essn, Pno);

INSERT INTO WORKS_ON (Essn, Pno, Hours )
VALUES 
( '123456789', 1, '32.5'),
( '123456789', 2, '7.5'),
( '666884444', 3, '40.0'),
( '453453453', 1, '20.0'),
( '453453453', 2, '20.0'),
( '333445555', 2, '10.0'),
( '333445555', 3, '10.0'),
( '333445555', 10, '10.0'),
( '333445555', 20, '10.0'),
( '999887777', 30, '30.0'),
( '999887777', 10, '10.0'),
( '987987987', 10, '35.0'),
( '987987987', 30, '5.0'),
( '987654321', 30, '20.0'),
( '987654321', 20, '15.0'),
( '888665555', 20, NULL)
```