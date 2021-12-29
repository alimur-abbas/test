# ASSIGNMENT OF MYSQL

* CREATE DATABASE command/keyword is used to create database.

```SQL 
CREATE DATABASE ASSINGMENT;
```
* To put in use  the database we need to  USE command/keyword.
```SQL
USE ASSINGMENT;
```
* Using CREATE TABLE command we can create a table.
 ```sql
 CREATE TABLE EMPLOYEES (
    E_ID INT PRIMARY KEY,
    E_NAME VARCHAR (20),
    E_ADDRESS VARCHAR(20),
    E_DEPARTMENT INT,
    E_SALARY INT ,CHECK( E_SALARY<= 100000)
    );
```
* To insert data into table we need INSERT INTO command/keyword.
```sql
INSERT INTO EMPLOYEES VALUES(1,'ALI','BHAWANIPATNA',01,99999);
INSERT INTO EMPLOYEES VALUES(2,'SAROJ','BHUBANESWAR',02,99998);
INSERT INTO EMPLOYEES VALUES(3,'SUBHASMITA','BHUBANESWAR',03,99997);
INSERT INTO EMPLOYEES VALUES(4,'ABC','BANGALORE',04,99996);
```
* To view  the contents of the table we use SELECT command/keyword('*' can further  be modify using attributes/columns name as per the requirement).

```SQL
 SELECT * FROM EMPLOYEES;
 ```
 * Changes in the table can be done using ALTER TABLE command/keyword(It too have many varient such as add constraint, modify,add coloumn ..... etc).

 ```SQL
 ALTER TABLE EMPLOYEES ADD column Date_of_joining year;
ALTER TABLE EMPLOYEES
 change
 Date_of_joining
 Date_of_joining year NOT NULL;
 ```
 * DROP TABLE Command/keyword is used to delete the table from the database.

 ```SQL
 CREATE TABLE ABC(
 ID INT NOT NULL
 );
 DROP table ABC; 
 ```
* DELETE command can be used to delete the tuple according to the WHERE condition.
 ```SQL
 DELETE FROM EMPLOYEES WHERE  E_ID = 5;
 ```
* UPDATE command can be used to update the tuple  according the WHERE condition.

* Without where condition all the tuples will be updated.
```SQL
UPDATE EMPLOYEES SET E_SALARY = 100000 WHERE  E_ID = 1 OR E_NAME = 'ALI';
```
* Below queries  is showing  the example  different types of joins(inner join, left join , right join , full join )

  1. Inner join:- Returns records that have matching values in both tables.

  2. Left(Outer) join:-Returns all records from the left table, and the matched records from the right table.

  3. Right(Outer) join:-Returns all records from the right table, and the matched records from the left table.

  4. Full(Outer) join:-Returns all records when there is a match in either left or right table.

```SQL
CREATE TABLE DEPARTMENT(
DEPARTMENT_ID INT UNIQUE,
DEPARTMENT_NAME VARCHAR(20)
);

INSERT INTO DEPARTMENT VALUES (1," BACK-END"),(2,"FRONT-END"),(3, "ACCOUNTS"),(4,"HR");


SELECT  E.E_NAME ,E.E_ADDRESS ,D.DEPARTMENT_NAME,D.DEPARTMENT_ID
FROM EMPLOYEES E  INNER JOIN  DEPARTMENT D 
ON E.E_DEPARTMENT = D. DEPARTMENT_ID; 

DELETE FROM DEPARTMENT WHERE DEPARTMENT_ID = 4;


SELECT  E.E_NAME ,E.E_ADDRESS ,D.DEPARTMENT_NAME,D.DEPARTMENT_ID 
FROM EMPLOYEES E  
LEFT JOIN  DEPARTMENT D 
ON E.E_DEPARTMENT = D. DEPARTMENT_ID ;

SELECT  E.E_NAME ,E.E_ADDRESS ,D.DEPARTMENT_NAME,D.DEPARTMENT_ID 
FROM EMPLOYEES E  
RIGHT JOIN  DEPARTMENT D 
ON E.E_DEPARTMENT = D. DEPARTMENT_ID ;

SELECT  E.E_NAME ,E.E_ADDRESS ,D.DEPARTMENT_NAME,D.DEPARTMENT_ID 
FROM EMPLOYEES E  
JOIN  DEPARTMENT D 
ON E.E_DEPARTMENT = D. DEPARTMENT_ID ;
```
* FOREIGN KEY :-A FOREIGN KEY is a field (or collection of fields) in one table, that refers to the PRIMARY KEY in another table.

  The table with the foreign key is called the child table, and the table with the primary key is called the referenced or parent table.

  Shown below is the example query for FOREIGN KEY

```SQL
CREATE TABLE Persons (
    ID int NOT NULL,
    LastName varchar(255) NOT NULL,
    FirstName varchar(255),
    Age int,
    PRIMARY KEY (ID)
);

CREATE TABLE Orders (
    OrderID int NOT NULL,
    OrderNumber int NOT NULL,
    PersonID int,
    PRIMARY KEY (OrderID),
    FOREIGN KEY (PersonID) REFERENCES Persons(ID)
);
```
* DROP DATABASE command/keyword is used to the delete the database.

```SQL
DROP  database ASSINGMENT;
```







