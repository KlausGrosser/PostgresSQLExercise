# PostgresSQLExercise 1
> Create a database - “Digital Career Institute”  
> rename it to dci  
> _Hint:_ Use ALTER DATABASE command with RENAME TO.  
> Create four schemas - “students”, “courses”, “partners”, “sales”  
> Create at least two tables in each schema, and fill each with at least four rows.  
> use all DDL commands in some way from your choice

-   CREATE
-   ALTER
-   DROP
-   TRUNCATE
-   RENAME

SOLUTION:

klausgrosser=# create database Digital_Career_Institute;

CREATE DATABASE

klausgrosser=# ALTER DATABASE Digital_Career_Institute RENAME TO dci;

ALTER DATABASE

klausgrosser=# CREATE SCHEMA students;

CREATE SCHEMA

klausgrosser=# CREATE SCHEMA courses;

CREATE SCHEMA

klausgrosser=# CREATE SCHEMA partners;

CREATE SCHEMA

klausgrosser=# CREATE SCHEMA sales;

CREATE SCHEMA

klausgrosser=# create table sales.members(name varchar(255), area varchar(255));        

CREATE TABLE

klausgrosser=# create table sales.employees(name varchar(255), area varchar(255));

CREATE TABLE

klausgrosser=# create table students.students(name varchar(255), grades int);

CREATE TABLE

klausgrosser=# create table students.courses(courseName varchar(255), teacherName int);

CREATE TABLE

klausgrosser=# create table courses.students(name varchar(255), grades int);

CREATE TABLE

klausgrosser=# create table courses.teachers(name varchar(255), assignedStudents int);

CREATE TABLE

klausgrosser=# create table partners.sponsors(name varchar(255), area varchar(255));

CREATE TABLE

klausgrosser=# create table partners.charities(name varchar(255), area varchar(255));

CREATE TABLE

klausgrosser=# INSERT INTO sales.members VALUES ('John', 'San Francisco'), ('Peter', 'Hamburg'),('Laura','Berlin'),('Lisa', 'Paris');

INSERT 0 4

klausgrosser=# INSERT INTO sales.employees VALUES ('David', 'Berlin'), ('Ruth', 'Mexico'),('Betty','USA'),('Rick', 'UK');

INSERT 0 4

klausgrosser=# INSERT INTO students.students VALUES ('David', '7'), ('Ruth', '9'),('Betty','8'),('Rick', '6');

INSERT 0 4

klausgrosser=# INSERT INTO students.courses VALUES ('Kotlin','8'), ('Go', '6'),('Python','9'),('Java', '10');     

INSERT 0 4

klausgrosser=# INSERT INTO courses.students VALUES ('David', '7'), ('Ruth', '9'),('Betty','8'),('Rick', '6');       

INSERT 0 4

klausgrosser=# INSERT INTO courses.teachers VALUES ('Chandler', '4'), ('Rachel', '9'),('Phoebe','5'),('Janice', '6'); 

INSERT 0 4

klausgrosser=# INSERT INTO partners.sponsors VALUES ('Tesla', 'Berlin'), ('Bimbo', 'Mexico'),('NASA','USA'),('MAPS', 'UK');

INSERT 0 4

klausgrosser=# INSERT INTO partners.charities VALUES ('Red Cross', 'Berlin'), ('GreenPeace', 'Mexico'),('PETA','USA'),('A.A.', 'UK');

INSERT 0 4

##Exercise 2

Exercise 2 Solution:
testdb=# CREATE TABLE countries (country_id int, country_name varchar(80), region_id int);

CREATE TABLE

CREATE TABLE IF NOT EXISTS countries ( 
country_id int),
country_name varchar(80),
region_id int
);

NOTICE:  relation "countries" already exists, skipping
CREATE TABLE


CREATE TABLE dup_countries AS SELECT * FROM countries WHERE 1=2;

SELECT 0

CREATE TABLE dup_countries AS SELECT * FROM countries;

SELECT 0

CREATE TABLE IF NOT EXISTS countries ( 
country_id int NOT NULL,
country_name varchar(80) NOT NULL,
region_id int NOT NULL
);

CREATE TABLE

testdb=# CREATE TABLE IF NOT EXISTS jobs ( 
testdb(# JOB_ID varchar(10) NOT NULL , 
testdb(# JOB_TITLE varchar(35) NOT NULL, 
testdb(# MIN_SALARY decimal(6,0), 
testdb(# MAX_SALARY decimal(6,0) 
testdb(# CHECK(MAX_SALARY<=25000)
testdb(# );

CREATE TABLE

CREATE TABLE IF NOT EXISTS countries ( 
COUNTRY_ID varchar(2),
COUNTRY_NAME varchar(40)
CHECK(COUNTRY_NAME IN('Italy','India','China')) ,
REGION_ID decimal(10,0)
);

CREATE TABLE

testdb=# CREATE TABLE IF NOT EXISTS countries ( 
testdb(# COUNTRY_ID varchar(2) NOT NULL,
testdb(# COUNTRY_NAME varchar(40) NOT NULL,
testdb(# REGION_ID decimal(10,0) NOT NULL,
testdb(# UNIQUE(COUNTRY_ID)
testdb(# );

CREATE TABLE

testdb=# CREATE TABLE IF NOT EXISTS jobs ( 
testdb(# JOB_ID varchar(10) NOT NULL UNIQUE, 
testdb(# JOB_TITLE varchar(35) NOT NULL DEFAULT ' ', 
testdb(# MIN_SALARY decimal(6,0) DEFAULT 8000, 
testdb(# MAX_SALARY decimal(6,0) DEFAULT NULL
testdb(# );

CREATE TABLE

testdb=# CREATE TABLE IF NOT EXISTS countries ( 
testdb(# COUNTRY_ID varchar(2) NOT NULL UNIQUE PRIMARY KEY,
testdb(# COUNTRY_NAME varchar(40) NOT NULL,
testdb(# REGION_ID decimal(10,0) NOT NULL
testdb(# );

CREATE TABLE

testdb=# CREATE TABLE IF NOT EXISTS countries (
testdb(# COUNTRY_ID varchar(2) NOT NULL UNIQUE DEFAULT '',
testdb(# COUNTRY_NAME varchar(40) DEFAULT NULL,
testdb(# REGION_ID decimal(10,0) NOT NULL,
testdb(# PRIMARY KEY (COUNTRY_ID,REGION_ID));
NOTICE:  relation "countries" already exists, skipping

CREATE TABLE



