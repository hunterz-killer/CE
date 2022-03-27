# Lab Sheet - 6

# Question 1 - Create Table
```
CREATE TABLE StudentDetails (
 	RollNo Varchar PRIMARY KEY, 
 	Stu_Name Varchar, 
 	Gender varchar, 
 	Branch varchar,
 	District varchar, 
 	State_name varchar, 
 	HorD varchar, 
 	Admission_Year int, 
 	CGPA float, 
 	Batch char);
```

# Question 2 - Inserting Data into Table
```
COPY studentdetails FROM '<File Path>.csv' CSV HEADER;
```

# Question 3 - Fill in the blanks
![image](https://user-images.githubusercontent.com/82221655/160280613-ca34815f-9866-449c-944b-528030ad0744.png)

<b>Option - A </b>
```
SELECT stu_name FROM studentdetails WHERE rolino='B14010';
```
<b>Option - B </b>
```
SELECT count(rollno) as Stu_City FROM studentdetails WHERE district='Thrissur';
```
<b>Option - C </b>
```
SELECT count(rollno) as Stu_state FROM studentdetails WHERE state_name='ANDHRA PRADESH';
```
<b>Option - D </b>
```
SELECT COUNT(ROLLNO) AS ME_2014 FROM studentdetails WHERE branch='ME' AND admission_year='2014';
```
<b>Option - E </b>
```
SELECT COUNT(ROLLNO) AS CSE_2014_A FROM studentdetails WHERE branch='CSE' AND admission_year='2014' AND batch='A';
```

# Question 4 - Fill in the Table

### Table 1
![image](https://user-images.githubusercontent.com/82221655/160280820-e3ceac01-dcea-444a-89d1-41f6cbb1cc62.png)

<b>Row 1</b>
```
SELECT 
(SELECT COUNT(ROLLNO) FROM studentdetails WHERE branch='CSE' AND admission_year='2012') AS CSE,
(SELECT COUNT(ROLLNO) FROM studentdetails WHERE branch='ME' AND admission_year='2012') AS ME,
(SELECT COUNT(ROLLNO) FROM studentdetails WHERE branch='EEE' AND admission_year='2012') AS EEE,
(SELECT COUNT(ROLLNO) FROM studentdetails WHERE branch='ECE' AND admission_year='2012') AS ECE;
```
<b>Row 2</b>
```
SELECT 
(SELECT COUNT(ROLLNO) FROM studentdetails WHERE branch='CSE' AND admission_year='2010') AS CSE,
(SELECT COUNT(ROLLNO) FROM studentdetails WHERE branch='ME' AND admission_year='2010') AS ME,
(SELECT COUNT(ROLLNO) FROM studentdetails WHERE branch='EEE' AND admission_year='2010') AS EEE,
(SELECT COUNT(ROLLNO) FROM studentdetails WHERE branch='ECE' AND admission_year='2010') AS ECE;
```
