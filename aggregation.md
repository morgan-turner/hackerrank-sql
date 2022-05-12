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
