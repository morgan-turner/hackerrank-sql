# Aggregation Problems
**my solutions to Hacker Rank's SQL problems using MySQL syntax**

[<h3>The Count Function</h3>](https://www.hackerrank.com/challenges/revising-aggregations-the-count-function/)
Query a count of the number of cities in CITY having a Population larger than 100,000. 

The CITY table is described as follows: 

|  Field | Type |
|-------|------|
| ID | INTEGER |
| NAME | VARCHAR(17) |
| COUNTRYCODE | VARCHAR(3) |
| DISTRICT | VARCHAR(20) |
| POPULATION | NUMBER |

**SOLUTION:**
```sql
SELECT COUNT(name)
FROM city
WHERE population > 100000
```


[<h3>The Sum Function</h3>](https://www.hackerrank.com/challenges/revising-aggregations-sum/)
Query the total population of all cities in CITY where District is California. 

The CITY table is described as follows: 

|  Field | Type |
|-------|------|
| ID | INTEGER |
| NAME | VARCHAR(17) |
| COUNTRYCODE | VARCHAR(3) |
| DISTRICT | VARCHAR(20) |
| POPULATION | NUMBER |

**SOLUTION:**
```sql
SELECT SUM(population)
FROM city
WHERE district = 'California'
```


[<h3>The Average Function</h3>](https://www.hackerrank.com/challenges/revising-aggregations-the-average-function/)
Query the average population of all cities in CITY where District is California. 

The CITY table is described as follows: 

|  Field | Type |
|-------|------|
| ID | INTEGER |
| NAME | VARCHAR(17) |
| COUNTRYCODE | VARCHAR(3) |
| DISTRICT | VARCHAR(20) |
| POPULATION | NUMBER |

**SOLUTION:**
```sql
SELECT AVG(population)
FROM city
WHERE district = 'California'
```


[<h3>Average Population</h3>](https://www.hackerrank.com/challenges/average-population/)
Query the average population for all cities in CITY, rounded down to the nearest integer.

The CITY table is described as follows: 

|  Field | Type |
|-------|------|
| ID | INTEGER |
| NAME | VARCHAR(17) |
| COUNTRYCODE | VARCHAR(3) |
| DISTRICT | VARCHAR(20) |
| POPULATION | NUMBER |

**SOLUTION:**
```sql
SELECT ROUND(AVG(population)) as average_pop
FROM city
```


[<h3>Japan Population</h3>](https://www.hackerrank.com/challenges/japan-population/)
Query the sum of the populations for all Japanese cities in CITY. The COUNTRYCODE for Japan is JPN.

The CITY table is described as follows: 

|  Field | Type |
|-------|------|
| ID | INTEGER |
| NAME | VARCHAR(17) |
| COUNTRYCODE | VARCHAR(3) |
| DISTRICT | VARCHAR(20) |
| POPULATION | NUMBER |

**SOLUTION:**
```sql
SELECT SUM(population)
FROM city
WHERE countrycode = 'JPN'
```


[<h3>Population Density Difference</h3>](https://www.hackerrank.com/challenges/japan-population/)
Query the difference between the maximum and minimum populations in CITY.

|  Field | Type |
|-------|------|
| ID | INTEGER |
| NAME | VARCHAR(17) |
| COUNTRYCODE | VARCHAR(3) |
| DISTRICT | VARCHAR(20) |
| POPULATION | NUMBER |

**SOLUTION:**
```sql
SELECT MAX(population) - MIN(population) as pop_difference
FROM city
```


[<h3>The Blunder</h3>](https://www.hackerrank.com/challenges/the-blunder/)
Samantha was tasked with calculating the average monthly salaries for all employees in the EMPLOYEES table, but did not realize her keyboard's 0 key was broken until after completing the calculation.
She wants your help finding the difference between her miscalculation (using salaries with any zeros removed), and the actual average salary.
Write a query calculating the amount of error (i.e.: actual - miscalculated average monthly salaries), and round it up to the next integer.

The EMPLOYEES table is described as follows:

|  Column | Type |
|-------|------|
| ID | INTEGER |
| NAME | STRING |
| SALARY | INTEGER |

**SOLUTION:**
```sql
SELECT ROUND(AVG(salary)) - ROUND(AVG(REPLACE(salary, '0', '')))
FROM employees
```


[<h3>Top Earners</h3>](https://www.hackerrank.com/challenges/earnings-of-employees/)
We define an employee's total earnings to be their monthly salary x months worked, and the maximum total earnings to be the maximum total earnings for any employee in the Employee table. Write a query to find the maximum total earnings for all employees as well as the total number of employees who have maximum total earnings. Then print these values as 2 space-separated integers.

The EMPLOYEE table containing employee data for a company is described as follows:

|  Column | Type |
|-------|------|
| employee_id | INTEGER |
| name | STRING |
| months | INTEGER |
| salary | INTEGER |

where employee_id is an employee's ID number, name is their name, months is the total number of months they've been working for the company, and salary is the their monthly salary.

**SOLUTION:**
```sql
SELECT salary * months, COUNT(salary * months)
FROM employee
GROUP BY salary * months
ORDER BY salary * months DESC
LIMIT 1
```


[<h3>Weather Observation Station 13</h3>](https://www.hackerrank.com/challenges/weather-observation-station-13/)
Query the sum of Northern Latitudes (LAT_N) from STATION having values greater than 38.7880 and less than 137.2345. Truncate your answer to 4 decimal places.

The STATION table is described as follows:

|  Field | Type |
|-------|------|
| ID | NUMBER |
| CITY | VARCHAR2(21) |
| STATE | VARCHAR2(2) |
| LAT_N | NUMBER |
| LONG_W | NUMBER |

where LAT_N is the northern latitude and LONG_W is the western longitude. 

**SOLUTION:**
```sql
SELECT ROUND(SUM(lat_n), 4)
FROM station
WHERE lat_n > 38.7880 AND lat_n < 137.2345
```


[<h3>Weather Observation Station 14</h3>](https://www.hackerrank.com/challenges/weather-observation-station-14/)
Query the greatest value of the Northern Latitudes (LAT_N) from STATION that is less than 137.2345. Truncate your answer to 4 decimal places.

The STATION table is described as follows:

|  Field | Type |
|-------|------|
| ID | NUMBER |
| CITY | VARCHAR2(21) |
| STATE | VARCHAR2(2) |
| LAT_N | NUMBER |
| LONG_W | NUMBER |

where LAT_N is the northern latitude and LONG_W is the western longitude. 

**SOLUTION:**
```sql
SELECT ROUND(MAX(lat_n), 4)
FROM station
WHERE lat_n < 137.2345
```


[<h3>Weather Observation Station 15</h3>](https://www.hackerrank.com/challenges/weather-observation-station-15/)
Query the Western Longitude (LONG_W) for the largest Northern Latitude (LAT_N) in STATION that is less than 137.2345. Truncate your answer to 4 decimal places.

The STATION table is described as follows:

|  Field | Type |
|-------|------|
| ID | NUMBER |
| CITY | VARCHAR2(21) |
| STATE | VARCHAR2(2) |
| LAT_N | NUMBER |
| LONG_W | NUMBER |

where LAT_N is the northern latitude and LONG_W is the western longitude. 

**SOLUTION:**
```sql
SELECT ROUND(long_w, 4)
FROM station
WHERE lat_n < 137.2345 
ORDER BY lat_n DESC
LIMIT 1
```


[<h3>Weather Observation Station 16</h3>](https://www.hackerrank.com/challenges/weather-observation-station-16/)
Query the smallest Northern Latitude (LAT_N) from STATION that is greater than 38.7780. Round your answer to 4 decimal places.

The STATION table is described as follows:

|  Field | Type |
|-------|------|
| ID | NUMBER |
| CITY | VARCHAR2(21) |
| STATE | VARCHAR2(2) |
| LAT_N | NUMBER |
| LONG_W | NUMBER |

where LAT_N is the northern latitude and LONG_W is the western longitude. 

**SOLUTION:**
```sql
SELECT ROUND(MIN(lat_n), 4)
FROM station
WHERE lat_n > 38.7780
```
