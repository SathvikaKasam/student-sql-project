This project is a simple SQL-based Student Information System.
It demonstrates how to design tables, insert data, and run queries on a database using SQLite.



DataBase Schema
The project uses three main tables:

1.Students – Stores student details

CREATE TABLE "STUDENT" (
	"STUDENT_ID"	INTEGER NOT NULL,
	"NAME"	VARCHAR(250),
	"AGE"	INTEGER,
	"GENDER"	VARCHAR(10),
	PRIMARY KEY("STUDENT_ID")
);

2.Courses – Stores course details

CREATE TABLE COURSES (
    "COURSE_ID" INTEGER NOT NULL PRIMARY KEY,
    "COURSE_NAME" VARCHAR(200),
    "CREDITS" INTEGER);


3.Enrollments – Stores student enrollments and grades

CREATE TABLE "ENROLLMENTS" (
	"ENROLLMENT_ID"	INTEGER,
	"STUDENT_ID"	INTEGER,
	"COURSE_ID"	INTEGER,
	"GRADE"	TEXT,
	PRIMARY KEY("ENROLLMENT_ID"),
	FOREIGN KEY("COURSE_ID") REFERENCES "COURSES"("COURSE_ID"),
	FOREIGN KEY("STUDENT_ID") REFERENCES "STUDENT"("STUDENT_ID")
);


Files Included

schema.sql → Table creation scripts

insert_data.sql → Data insertion scripts

queries.sql → SQL queries used in the project

outputs.txt → Outputs of queries


How To Run

1.Open sqlite3

2.Run SQL files in order


.header ON(to Display the columnn names)
.mode columns(It changes how query results are displayed.)
.read schema.sql
.read insert_data.sql
.read queries.sql


