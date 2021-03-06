# Basic Select Problems
**my solutions to Hacker Rank's SQL problems using MySQL syntax**

[<h3>Weather Observation Station 1</h3>](https://www.hackerrank.com/challenges/weather-observation-station-1/)
Query a list of CITY and STATE from the STATION table.
<br>The STATION table is described as follows:

|  Field | Type |
|-------|------|
| ID  | NUMBER |
| CITY | VARCHAR2(21)   |
| STATE  | VARCHAR2(2)  |
| LAT_N |  NUMBER |
| LONG_W | NUMBER |

where LAT_N is the northern latitude and LONG_W is the western longitude.

**SOLUTION:**
```sql
SELECT city, state
FROM station
```

[<h3>Weather Observation Station 2</h3>](https://www.hackerrank.com/challenges/weather-observation-station-2/)
Query the following two values from the STATION table:
1) The sum of all values in LAT_N rounded to a scale of decimal places.
2) The sum of all values in LONG_W rounded to a scale of decimal places.
<br>The STATION table is described as follows:

|  Field | Type |
|-------|------|
| ID  | NUMBER |
| CITY | VARCHAR2(21)   |
| STATE  | VARCHAR2(2)  |
| LAT_N |  NUMBER |
| LONG_W | NUMBER |

where LAT_N is the northern latitude and LONG_W is the western longitude.
Your results must be in the form: lat, lon

**SOLUTION:**
```sql
SELECT ROUND(SUM(Lat_N), 2) as lat, ROUND(SUM(Long_W),2) as lon
FROM station
```

[<h3>Weather Observation Station 3</h3>](https://www.hackerrank.com/challenges/weather-observation-station-3/)
Query a list of CITY names from STATION for cities that have an even ID number. Print the results in any order, but exclude duplicates from the answer.
<br>The STATION table is described as follows:

|  Field | Type |
|-------|------|
| ID  | NUMBER |
| CITY | VARCHAR2(21)   |
| STATE  | VARCHAR2(2)  |
| LAT_N |  NUMBER |
| LONG_W | NUMBER |

where LAT_N is the northern latitude and LONG_W is the western longitude.

**SOLUTION:**
```sql
SELECT DISTINCT city
FROM station
WHERE id%2=0
```

[<h3>Weather Observation Station 4</h3>](https://www.hackerrank.com/challenges/weather-observation-station-4/)
Find the difference between the total number of CITY entries in the table and the number of distinct CITY entries in the table.
<br>The STATION table is described as follows:

|  Field | Type |
|-------|------|
| ID  | NUMBER |
| CITY | VARCHAR2(21)   |
| STATE  | VARCHAR2(2)  |
| LAT_N |  NUMBER |
| LONG_W | NUMBER |

where LAT_N is the northern latitude and LONG_W is the western longitude.

**SOLUTION:**
```sql
SELECT COUNT(city) - COUNT(DISTINCT city)
FROM station
```

[<h3>Weather Observation Station 5</h3>](https://www.hackerrank.com/challenges/weather-observation-station-5/)
Query the two cities in STATION with the shortest and longest CITY names, as well as their respective lengths (i.e.: number of characters in the name). If there is more than one smallest or largest city, choose the one that comes first when ordered alphabetically.
<br>The STATION table is described as follows:

|  Field | Type |
|-------|------|
| ID  | NUMBER |
| CITY | VARCHAR2(21)   |
| STATE  | VARCHAR2(2)  |
| LAT_N |  NUMBER |
| LONG_W | NUMBER |

where LAT_N is the northern latitude and LONG_W is the western longitude.

**SOLUTION:**
```sql
SELECT city, LENGTH (city)
FROM station
ORDER BY LENGTH(city) ASC, CITY ASC
LIMIT 1;

SELECT city, LENGTH(city)
FROM station
ORDER BY LENGTH(city) DESC, CITY ASC
LIMIT 1
```

[<h3>Weather Observation Station 6</h3>](https://www.hackerrank.com/challenges/weather-observation-station-6/)
Query the list of CITY names starting with vowels (i.e., a, e, i, o, or u) from STATION. Your result cannot contain duplicates.
<br>The STATION table is described as follows:

|  Field | Type |
|-------|------|
| ID  | NUMBER |
| CITY | VARCHAR2(21)   |
| STATE  | VARCHAR2(2)  |
| LAT_N |  NUMBER |
| LONG_W | NUMBER |

where LAT_N is the northern latitude and LONG_W is the western longitude.

**SOLUTION:**
```sql
SELECT DISTINCT city
FROM station
WHERE city LIKE 'a%' OR city LIKE 'e%' OR city LIKE 'i%' OR city LIKE 'o%' OR city LIKE 'u%'
```

[<h3>Weather Observation Station 7</h3>](https://www.hackerrank.com/challenges/weather-observation-station-7/)
Query the list of CITY names ending with vowels (a, e, i, o, u) from STATION. Your result cannot contain duplicates.
<br>The STATION table is described as follows:

|  Field | Type |
|-------|------|
| ID  | NUMBER |
| CITY | VARCHAR2(21)   |
| STATE  | VARCHAR2(2)  |
| LAT_N |  NUMBER |
| LONG_W | NUMBER |

where LAT_N is the northern latitude and LONG_W is the western longitude.

**SOLUTION:**
```sql
SELECT DISTINCT city
FROM station
WHERE city LIKE '%a' OR city LIKE '%e' OR city LIKE '%i' OR city LIKE '%o' OR city LIKE '%u'
```

[<h3>Weather Observation Station 8</h3>](https://www.hackerrank.com/challenges/weather-observation-station-8/)
Query the list of CITY names from STATION which have vowels (i.e., a, e, i, o, and u) as both their first and last characters. Your result cannot contain duplicates.
<br>The STATION table is described as follows:

|  Field | Type |
|-------|------|
| ID  | NUMBER |
| CITY | VARCHAR2(21)   |
| STATE  | VARCHAR2(2)  |
| LAT_N |  NUMBER |
| LONG_W | NUMBER |

where LAT_N is the northern latitude and LONG_W is the western longitude.

**SOLUTION:**
```sql
SELECT DISTINCT city
FROM station
WHERE 
(city LIKE 'a%' OR 
city LIKE 'e%' OR 
city LIKE 'i%' OR 
city LIKE 'o%' OR 
city LIKE 'u%')
AND 
(city LIKE '%a' OR 
city LIKE '%e' OR 
city LIKE '%i' OR 
city LIKE '%o' OR 
city LIKE '%u')
```

[<h3>Weather Observation Station 9</h3>](https://www.hackerrank.com/challenges/weather-observation-station-9/)
Query the list of CITY names from STATION that do not start with vowels. Your result cannot contain duplicates.
The STATION table is described as follows:

|  Field | Type |
|-------|------|
| ID  | NUMBER |
| CITY | VARCHAR2(21)   |
| STATE  | VARCHAR2(2)  |
| LAT_N |  NUMBER |
| LONG_W | NUMBER |

where LAT_N is the northern latitude and LONG_W is the western longitude.
<br>The STATION table is described as follows:

**SOLUTION:**
```sql
SELECT DISTINCT city
FROM station
WHERE 
(city NOT LIKE 'a%' AND 
city NOT LIKE 'e%' AND
city NOT LIKE 'i%' AND
city NOT LIKE 'o%' AND
city NOT LIKE 'u%')
```

[<h3>Weather Observation Station 10</h3>](https://www.hackerrank.com/challenges/weather-observation-station-10/)
Query the list of CITY names from STATION that do not end with vowels. Your result cannot contain duplicates.
<br>The STATION table is described as follows:

|  Field | Type |
|-------|------|
| ID  | NUMBER |
| CITY | VARCHAR2(21)   |
| STATE  | VARCHAR2(2)  |
| LAT_N |  NUMBER |
| LONG_W | NUMBER |

where LAT_N is the northern latitude and LONG_W is the western longitude.

**SOLUTION:**
```sql
SELECT DISTINCT city
FROM station
WHERE 
(city NOT LIKE '%a' AND 
city NOT LIKE '%e' AND
city NOT LIKE '%i' AND
city NOT LIKE '%o' AND
city NOT LIKE '%u')
```

[<h3>Weather Observation Station 11</h3>](https://www.hackerrank.com/challenges/weather-observation-station-11/)
Query the list of CITY names from STATION that either do not start with vowels or do not end with vowels. Your result cannot contain duplicates.
<br>The STATION table is described as follows:

|  Field | Type |
|-------|------|
| ID  | NUMBER |
| CITY | VARCHAR2(21)   |
| STATE  | VARCHAR2(2)  |
| LAT_N |  NUMBER |
| LONG_W | NUMBER |

where LAT_N is the northern latitude and LONG_W is the western longitude.

**SOLUTION:**
```sql
SELECT DISTINCT city
FROM station
WHERE 
(city NOT LIKE 'a%' AND 
city NOT LIKE 'e%' AND
city NOT LIKE 'i%' AND
city NOT LIKE 'o%' AND
city NOT LIKE 'u%')
OR
(city NOT LIKE '%a' AND 
city NOT LIKE '%e' AND
city NOT LIKE '%i' AND
city NOT LIKE '%o' AND
city NOT LIKE '%u')
```

[<h3>Weather Observation Station 12</h3>](https://www.hackerrank.com/challenges/weather-observation-station-12/)
Query the list of CITY names from STATION that do not start with vowels and do not end with vowels. Your result cannot contain duplicates.
<br>The STATION table is described as follows:

|  Field | Type |
|-------|------|
| ID  | NUMBER |
| CITY | VARCHAR2(21)   |
| STATE  | VARCHAR2(2)  |
| LAT_N |  NUMBER |
| LONG_W | NUMBER |

where LAT_N is the northern latitude and LONG_W is the western longitude.

**SOLUTION:**
```sql
SELECT DISTINCT city
FROM station
WHERE 
(city NOT LIKE 'a%' AND 
city NOT LIKE 'e%' AND
city NOT LIKE 'i%' AND
city NOT LIKE 'o%' AND
city NOT LIKE 'u%')
AND
(city NOT LIKE '%a' AND 
city NOT LIKE '%e' AND
city NOT LIKE '%i' AND
city NOT LIKE '%o' AND
city NOT LIKE '%u')
```

[<h3>Higher than 75% Marks</h3>](https://www.hackerrank.com/challenges/more-than-75-marks/)
Query the Name of any student in STUDENTS who scored higher than 75 marks. Order your output by the last three characters of each name. 
If two or more students both have names ending in the same last three characters (i.e.: Bobby, Robby, etc.), secondary sort them by ascending ID.
<br>The STUDENTS table is described as follows: 

|  Column | Type |
|-------|------|
| ID  | INTEGER |
| NAME | STRING |
| MARKS  | INTEGER |

**SOLUTION:**
```sql
SELECT name
FROM students
WHERE marks > 75
ORDER BY RIGHT(name, 3), id
```

[<h3>Employee Names</h3>](https://www.hackerrank.com/challenges/name-of-employees/)
Write a query that prints a list of employee names (i.e.: the name attribute) from the Employee table in alphabetical order.
<br>The Employee table containing employee data for a company is described as follows: 


|  Column | Type |
|-------|------|
| EMPLOYEE_ID  | INTEGER |
| NAME | STRING |
| MONTHS  | INTEGER |
| SALARY | INTEGER |

where employee_id is an employee's ID number, name is their name, months is the total number of months they've been working for the company, and salary is their monthly salary.

**SOLUTION:**
```sql
SELECT name
FROM employee
ORDER BY name
```

[<h3>Employee Salaries</h3>](https://www.hackerrank.com/challenges/salary-of-employees/)
Write a query that prints a list of employee names (i.e.: the name attribute) for employees in Employee having a salary greater than $2000 per month who have been employees for less than 10 months. 
Sort your result by ascending employee_id.
<br>The Employee table containing employee data for a company is described as follows: 


|  Column | Type |
|-------|------|
| EMPLOYEE_ID  | INTEGER |
| NAME | STRING |
| MONTHS  | INTEGER |
| SALARY | INTEGER |

where employee_id is an employee's ID number, name is their name, months is the total number of months they've been working for the company, and salary is their monthly salary.

**SOLUTION:**
```sql
SELECT name
FROM employee
WHERE salary>2000 AND months<10
ORDER BY employee_id
```

