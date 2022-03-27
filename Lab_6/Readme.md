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

### Table 2
![image](https://user-images.githubusercontent.com/82221655/160280981-6a3d1d34-7cc2-4bd6-af5c-856c2057d1dd.png)
<b>Row 1</b>
```
SELECT 
(SELECT COUNT(ROLLNO) FROM studentdetails WHERE branch='CSE' AND admission_year='2014' AND cgpa>9) AS CSE,
(SELECT COUNT(ROLLNO) FROM studentdetails WHERE branch='ME' AND admission_year='2014' AND cgpa>9) AS ME,
(SELECT COUNT(ROLLNO) FROM studentdetails WHERE branch='EEE' AND admission_year='2014' AND cgpa>9) AS EEE,
(SELECT COUNT(ROLLNO) FROM studentdetails WHERE branch='ECE' AND admission_year='2014' AND cgpa>9) AS ECE;
```

<b>Row 2</b>
```
SELECT 
(SELECT COUNT(ROLLNO) FROM studentdetails WHERE branch='CSE' AND hord='Hostelite' AND cgpa<6) AS CSE,
(SELECT COUNT(ROLLNO) FROM studentdetails WHERE branch='ME' AND hord='Hostelite' AND cgpa<6) AS ME,
(SELECT COUNT(ROLLNO) FROM studentdetails WHERE branch='EEE' AND hord='Hostelite' AND cgpa<6) AS EEE,
(SELECT COUNT(ROLLNO) FROM studentdetails WHERE branch='ECE' AND hord='Hostelite' AND cgpa<6) AS ECE;
```

<b>Row 3</b>
```
SELECT 
(SELECT COUNT(ROLLNO) FROM studentdetails WHERE branch='CSE' AND hord='Dayscholar' AND cgpa>8) AS CSE,
(SELECT COUNT(ROLLNO) FROM studentdetails WHERE branch='ME' AND hord='Dayscholar' AND cgpa>8) AS ME,
(SELECT COUNT(ROLLNO) FROM studentdetails WHERE branch='EEE' AND hord='Dayscholar' AND cgpa>8) AS EEE,
(SELECT COUNT(ROLLNO) FROM studentdetails WHERE branch='ECE' AND hord='Dayscholar' AND cgpa>8) AS ECE;
```

<b>Row 4</b>
```
SELECT 
(SELECT COUNT(ROLLNO) FROM studentdetails WHERE branch='CSE' AND gender='Female' AND cgpa BETWEEN 5 and 7) AS CSE,
(SELECT COUNT(ROLLNO) FROM studentdetails WHERE branch='ME' AND gender='Female' AND cgpa BETWEEN 5 and 7) AS ME,
(SELECT COUNT(ROLLNO) FROM studentdetails WHERE branch='EEE' AND gender='Female' AND cgpa BETWEEN 5 and 7) AS EEE,
(SELECT COUNT(ROLLNO) FROM studentdetails WHERE branch='ECE' AND gender='Female' AND cgpa BETWEEN 5 and 7) AS ECE;
```

### Table 3
![image](https://user-images.githubusercontent.com/82221655/160281126-53151c5c-c04c-4cb8-9565-851529102734.png)
<b>Row 1</b>
```
SELECT 
(SELECT AVG(cgpa) FROM studentdetails WHERE branch='CSE' AND admission_year='2014') AS CSE,
(SELECT AVG(cgpa) FROM studentdetails WHERE branch='ME' AND admission_year='2014') AS ME,
(SELECT AVG(cgpa) FROM studentdetails WHERE branch='EEE' AND admission_year='2014') AS EEE,
(SELECT AVG(cgpa) FROM studentdetails WHERE branch='ECE' AND admission_year='2014') AS ECE
```

<b>Row 2</b>
```
SELECT 
(SELECT AVG(cgpa) FROM studentdetails WHERE branch='CSE' AND admission_year='2014' AND gender='Female') AS CSE,
(SELECT AVG(cgpa) FROM studentdetails WHERE branch='ME' AND admission_year='2014' AND gender='Female') AS ME,
(SELECT AVG(cgpa) FROM studentdetails WHERE branch='EEE' AND admission_year='2014' AND gender='Female') AS EEE,
(SELECT AVG(cgpa) FROM studentdetails WHERE branch='ECE' AND admission_year='2014' AND gender='Female') AS ECE;
```

<b>Row 3</b>
```
SELECT 
(SELECT AVG(cgpa) FROM studentdetails WHERE branch='CSE' AND admission_year='2014' AND gender='Male') AS CSE,
(SELECT AVG(cgpa) FROM studentdetails WHERE branch='ME' AND admission_year='2014' AND gender='Male') AS ME,
(SELECT AVG(cgpa) FROM studentdetails WHERE branch='EEE' AND admission_year='2014' AND gender='Male') AS EEE,
(SELECT AVG(cgpa) FROM studentdetails WHERE branch='ECE' AND admission_year='2014' AND gender='Male') AS ECE;
```

<b>Row 4</b>
```
SELECT 
(SELECT AVG(cgpa) FROM studentdetails WHERE branch='CSE' AND admission_year='2014' AND hord='Hostelite') AS CSE,
(SELECT AVG(cgpa) FROM studentdetails WHERE branch='ME' AND admission_year='2014' AND hord='Hostelite') AS ME,
(SELECT AVG(cgpa) FROM studentdetails WHERE branch='EEE' AND admission_year='2014' AND hord='Hostelite') AS EEE,
(SELECT AVG(cgpa) FROM studentdetails WHERE branch='ECE' AND admission_year='2014' AND hord='Hostelite') AS ECE;
```

<b>Row 5</b>
```
SELECT 
(SELECT AVG(cgpa) FROM studentdetails WHERE branch='CSE' AND admission_year='2014' AND hord='Dayscholar') AS CSE,
(SELECT AVG(cgpa) FROM studentdetails WHERE branch='ME' AND admission_year='2014' AND hord='Dayscholar') AS ME,
(SELECT AVG(cgpa) FROM studentdetails WHERE branch='EEE' AND admission_year='2014' AND hord='Dayscholar') AS EEE,
(SELECT AVG(cgpa) FROM studentdetails WHERE branch='ECE' AND admission_year='2014' AND hord='Dayscholar') AS ECE;
```

### Table 4
![image](https://user-images.githubusercontent.com/82221655/160281304-391c386f-2887-4d0d-8c6d-92f9ae713a2a.png)
<b>Row 1</b>
```
SELECT 
(SELECT ROUND(CAST(MAX(cgpa) AS NUMERIC),2) FROM studentdetails WHERE branch='CSE' AND admission_year='2014') AS CSE,
(SELECT ROUND(CAST(MAX(cgpa) AS NUMERIC),2) FROM studentdetails WHERE branch='ME' AND admission_year='2014') AS ME,
(SELECT ROUND(CAST(MAX(cgpa) AS NUMERIC),2) FROM studentdetails WHERE branch='EEE' AND admission_year='2014') AS EEE,
(SELECT ROUND(CAST(MAX(cgpa) AS NUMERIC),2) FROM studentdetails WHERE branch='ECE' AND admission_year='2014') AS ECE;
```

<b>Row 2</b>
```
SELECT 
(SELECT ROUND(CAST(MIN(cgpa) AS NUMERIC),2) FROM studentdetails WHERE branch='CSE' AND admission_year='2014') AS CSE,
(SELECT ROUND(CAST(MIN(cgpa) AS NUMERIC),2) FROM studentdetails WHERE branch='ME' AND admission_year='2014') AS ME,
(SELECT ROUND(CAST(MIN(cgpa) AS NUMERIC),2) FROM studentdetails WHERE branch='EEE' AND admission_year='2014') AS EEE,
(SELECT ROUND(CAST(MIN(cgpa) AS NUMERIC),2) FROM studentdetails WHERE branch='ECE' AND admission_year='2014') AS ECE;
```

<b>Row 3</b>
```
SELECT 
(SELECT ROUND(CAST(MAX(cgpa) AS NUMERIC),2) FROM studentdetails WHERE branch='CSE' AND admission_year='2014' AND hord='Hostelite' AND gender='Male') AS CSE,
(SELECT ROUND(CAST(MAX(cgpa) AS NUMERIC),2) FROM studentdetails WHERE branch='ME' AND admission_year='2014' AND hord='Hostelite' AND gender='Male') AS ME,
(SELECT ROUND(CAST(MAX(cgpa) AS NUMERIC),2) FROM studentdetails WHERE branch='EEE' AND admission_year='2014' AND hord='Hostelite' AND gender='Male') AS EEE,
(SELECT ROUND(CAST(MAX(cgpa) AS NUMERIC),2) FROM studentdetails WHERE branch='ECE' AND admission_year='2014' AND hord='Hostelite' AND gender='Male') AS ECE;
```

<b>Row 4</b>
```
SELECT 
(SELECT ROUND(CAST(MIN(cgpa) AS NUMERIC),2) FROM studentdetails WHERE branch='CSE' AND admission_year='2014' AND hord='Dayscholar' AND district='Ernakulam') AS CSE,
(SELECT ROUND(CAST(MIN(cgpa) AS NUMERIC),2) FROM studentdetails WHERE branch='ME' AND admission_year='2014' AND hord='Dayscholar' AND district='Ernakulam') AS ME,
(SELECT ROUND(CAST(MIN(cgpa) AS NUMERIC),2) FROM studentdetails WHERE branch='EEE' AND admission_year='2014' AND hord='Dayscholar' AND district='Ernakulam') AS EEE,
(SELECT ROUND(CAST(MIN(cgpa) AS NUMERIC),2) FROM studentdetails WHERE branch='ECE' AND admission_year='2014' AND hord='Dayscholar' AND district='Ernakulam') AS ECE;
```

<b>Row 5</b>
```
SELECT 
(SELECT ROUND(CAST(MAX(cgpa) AS NUMERIC),2) FROM studentdetails WHERE branch='CSE' AND admission_year='2014' AND hord='Hostelite' AND gender='Female') AS CSE,
(SELECT ROUND(CAST(MAX(cgpa) AS NUMERIC),2) FROM studentdetails WHERE branch='ME' AND admission_year='2014' AND hord='Hostelite' AND gender='Female') AS ME,
(SELECT ROUND(CAST(MAX(cgpa) AS NUMERIC),2) FROM studentdetails WHERE branch='EEE' AND admission_year='2014' AND hord='Hostelite' AND gender='Female') AS EEE,
(SELECT ROUND(CAST(MAX(cgpa) AS NUMERIC),2) FROM studentdetails WHERE branch='ECE' AND admission_year='2014' AND hord='Hostelite' AND gender='Female') AS ECE;
```

<b>Row 6</b>
```
SELECT 
(SELECT ROUND(CAST(MAX(cgpa) AS NUMERIC),2) FROM studentdetails WHERE branch='CSE' AND admission_year='2014' AND hord='Hostelite' AND state_name='ANDHRA PRADESH') AS CSE,
(SELECT ROUND(CAST(MAX(cgpa) AS NUMERIC),2) FROM studentdetails WHERE branch='ME' AND admission_year='2014' AND hord='Hostelite' AND state_name='ANDHRA PRADESH') AS ME,
(SELECT ROUND(CAST(MAX(cgpa) AS NUMERIC),2) FROM studentdetails WHERE branch='EEE' AND admission_year='2014' AND hord='Hostelite' AND state_name='ANDHRA PRADESH') AS EEE,
(SELECT ROUND(CAST(MAX(cgpa) AS NUMERIC),2) FROM studentdetails WHERE branch='ECE' AND admission_year='2014' AND hord='Hostelite' AND state_name='ANDHRA PRADESH') AS ECE;
```

<b>Row 7</b>
```
SELECT 
(SELECT ROUND(CAST(MIN(cgpa) AS NUMERIC),2) FROM studentdetails WHERE branch='CSE' AND admission_year='2014' AND hord='Hostelite' AND district='Trivandrum' AND state_name='KERALA') AS CSE,
(SELECT ROUND(CAST(MIN(cgpa) AS NUMERIC),2) FROM studentdetails WHERE branch='ME' AND admission_year='2014' AND hord='Hostelite' AND district='Trivandrum' AND state_name='KERALA') AS ME,
(SELECT ROUND(CAST(MIN(cgpa) AS NUMERIC),2) FROM studentdetails WHERE branch='EEE' AND admission_year='2014' AND hord='Hostelite' AND district='Trivandrum' AND state_name='KERALA') AS EEE,
(SELECT ROUND(CAST(MIN(cgpa) AS NUMERIC),2) FROM studentdetails WHERE branch='ECE' AND admission_year='2014' AND hord='Hostelite' AND district='Trivandrum' AND state_name='KERALA') AS ECE;
```
