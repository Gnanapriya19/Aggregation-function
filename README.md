IMPLENTATION OF AGGREGATION FUNCTIONS, GROUPING AND 
ORDERING COMMANDS TO MANIPULATE TABLES IN A DATABASE 
 
 
AIM: 
To implement on aggregation functions, grouping and ordering commands to manipulate tables in a database. 
PROCEDURE: 
An aggregate function allows you to perform a calculation on a set of values to return a single 	scalar 	value. 	We 	often 	use 	aggregate 	functions 	with 	the GROUP BY and HAVING clauses of the SELECT statement. 
The following are the most commonly used SQL aggregate functions: 
AVG – calculates the average of a set of values. 
COUNT – counts rows in a specified table or view. 
MIN – gets the minimum value in a set of values. 
MAX – gets the maximum value in a set of values. 
SUM – calculates the sum of values. 
The SQL GROUP BY clause is used in collaboration with the SELECT statement to arrange identical data into groups. This GROUP BY clause follows the WHERE clause in a SELECT statement and precedes the ORDER BY clause. 
Syntax: 
SELECT column1, column2 
FROM table_name 
WHERE [ conditions ] 
GROUP BY column1, column2 
ORDER BY column1, column2 
The ORDER BY keyword is used to sort the result-set in ascending or descending order. 
The ORDER BY keyword sorts the records in ascending order by default. To sort the records in descending order, use the DESC keyword. 
 
Syntax; 
SELECT column1, column2, ... 
FROM table_name 
ORDER BY column1, column2, ... ASC|DESC;

COMMANDS: 
Let’s consider an employee table. We will perform the calculations on this table by using aggregate functions. 
Eid 	Ename 	Age 	City 	Salary 
E001 	ABC 	29 	Pune 	20000 
E002 	PQR 	30 	Pune 	30000 
E003 	LMN 	25 	Mumbai 	5000 
E004 	XYZ 	24 	Mumbai 	4000 
E005 	STU 	32 	Bangalore 	25000 
 
SQL> select AVG(salary) from employee; 
16800 
SQL> select MAX(salary) from employee; 
30000 
SQL> select MIN (salary) from employee; 
4000 
SQL>select SUM (salary) from employee where city=’Pune’; 
50000 
SQL> select COUNT(Empid) from employee; 
5 
SQL> select COUNT(*) from employee; 5 
 
Consider the CUSTOMERS table having the following records − 
+----+----------+-----+-----------+----------+ 
| ID | NAME     | AGE | ADDRESS   | SALARY   | 
+----+----------+-----+-----------+----------+ 
|  1 | Ramesh   |  32 | Ahmedabad |  2000.00 | 
|  2 | Khilan   |  25 | Delhi     |  1500.00 | 
|  3 | kaushik  |  23 | Kota      |  2000.00 | 
|  4 | Chaitali |  25 | Mumbai    |  6500.00 | 
|  5 | Hardik   |  27 | Bhopal    |  8500.00 | 
|  6 | Komal    |  22 | MP        |  4500.00 | 
|  7 | Muffy    |  24 | Indore    | 10000.00 | 
+----+----------+-----+-----------+----------+ 
SQL> SELECT NAME, SUM(SALARY) FROM CUSTOMERS 
   GROUP BY NAME; 
+----------+-------------+ 
| NAME     | SUM(SALARY) | 
+----------+-------------+ 
| Chaitali |     6500.00 | 
| Hardik   |     8500.00 | 
| kaushik  |     2000.00 | 
| Khilan   |     1500.00 | 
| Komal    |     4500.00 | 
| Muffy    |    10000.00 | 
| Ramesh   |     2000.00 | 
+----------+-------------+ 
SQL> SELECT * FROM CUSTOMERS 
   ORDER BY NAME, SALARY; 
+----+----------+-----+-----------+----------+ 
| ID | NAME     | AGE | ADDRESS   | SALARY   | +----+----------+-----+-----------+----------+ 
|  4 | Chaitali |  25 | Mumbai    |  6500.00 | 
|  5 | Hardik   |  27 | Bhopal    |  8500.00 | 
|  3 | kaushik  |  23 | Kota      |  2000.00 | 
|  2 | Khilan   |  25 | Delhi     |  1500.00 | 
|  6 | Komal    |  22 | MP        |  4500.00 | 
|  7 | Muffy    |  24 | Indore    | 10000.00 | 
|  1 | Ramesh   |  32 | Ahmedabad |  2000.00 | 
+----+----------+-----+-----------+----------+ 
SQL> SELECT * FROM CUSTOMERS 
   ORDER BY NAME DESC; 
+----+----------+-----+-----------+----------+ 
| ID | NAME     | AGE | ADDRESS   | SALARY   | 
+----+----------+-----+-----------+----------+ 
|  1 | Ramesh   |  32 | Ahmedabad |  2000.00 | 
|  7 | Muffy    |  24 | Indore    | 10000.00 | 
|  6 | Komal    |  22 | MP        |  4500.00 | 
|  2 | Khilan   |  25 | Delhi     |  1500.00 | 
|  3 | kaushik  |  23 | Kota      |  2000.00 | 
|  5 | Hardik   |  27 | Bhopal    |  8500.00 | 
|  4 | Chaitali |  25 | Mumbai    |  6500.00 | 
+----+----------+-----+-----------+----------+ 
 
 
RESULT: 
Thus the aggregation functions, grouping and ordering commands to manipulate tables in a database has been implemented and executes successfully. 
