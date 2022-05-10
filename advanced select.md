# Advanced Select Problems
**my solutions to Hacker Rank's SQL problems using MySQL syntax**

[<h3>Type of Triangle</h3>](https://www.hackerrank.com/challenges/what-type-of-triangle/)
Write a query identifying the type of each record in the TRIANGLES table using its three side lengths. 
Output one of the following statements for each record in the table:
- Equilateral: It's a triangle with sides of equal length.
- Isosceles: It's a triangle with sides of equal length.
- Scalene: It's a triangle with sides of differing lengths.
- Not A Triangle: The given values of A, B, and C don't form a triangle.

The TRIANGLES table is described as follows:

|  Column | Type |
|-------|------|
| A | INTEGER |
| B | INTEGER |
| C | INTEGER |

Each row in the table denotes the lengths of each of a triangle's three sides.

**SOLUTION:**
```sql
SELECT CASE             
            WHEN A + B > C AND B + C > A AND A + C > B THEN
                CASE 
                    WHEN A = B AND B = C THEN 'Equilateral'
                    WHEN A = B OR B = C OR A = C THEN 'Isosceles'
                    ELSE 'Scalene'
                END
            ELSE 'Not A Triangle'
            END
FROM TRIANGLES;
```

[<h3>The PADS</h3>](https://www.hackerrank.com/challenges/the-pads/)
Generate the following two result sets:
1) Query an alphabetically ordered list of all names in OCCUPATIONS, immediately followed by the first letter of each profession as a parenthetical (i.e.: enclosed in parentheses). 
For example: AnActorName(A), ADoctorName(D), AProfessorName(P), and ASingerName(S).
2) Query the number of ocurrences of each occupation in OCCUPATIONS. Sort the occurrences in ascending order, and output them in the following format:
<br>There are a total of [occupation_count] [occupation]s.

where [occupation_count] is the number of occurrences of an occupation in OCCUPATIONS and [occupation] is the lowercase occupation name. 
If more than one Occupation has the same [occupation_count], they should be ordered alphabetically.
Note: There will be at least two entries in the table for each type of occupation.

The OCCUPATIONS table is as follows:

|  Column | Type |
|-------|------|
| Name | STRING |
| Occupation | STRING |

Occupation will only contain one of the following values: Doctor, Professor, Singer or Actor.

**SOLUTION:**
```sql

```
