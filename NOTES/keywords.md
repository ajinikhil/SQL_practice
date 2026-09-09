__Keywords are not case-sensitive__
__Values are case sensitive depending on teh database__

## Select * / From

- `SELECT` - identifies the columns (or data) from a database
- `FROM` - Identifies the table we are conncting to
- `*` - Special command to select all the columns

You can also select a column by specifying the table name:
(this is mostly important when we combine multiple tables)

for example: 

table name: job_postings_fact
column names: job_title_short, job_location

The query would be:

````SELECT
        job_postings_fact.job_title_short,
        job_postings_fact.job_location
    FROM
        job_postings_fact

````

## LIMIT

The keyword limit is used to query only a certain amount of rows.
<br>
`Note`: We rarely uses SELECT * (all) , in most real life scenarios because it takes up a lot of processing power, instead we
would add syntax to `LIMIT` the number of values returned. 

The LIMIT should come after the SELECT and FROM statement. See the example below. 

````SELECT
        job_postings_fact.job_title_short,
        job_postings_fact.job_location
    FROM
        job_postings_fact
    LIMIT 5
````

## DISTINCT

- Distinct keyword is used to get unique rows
- This keywork is very resource intensive

```
SELECT DISTINCT
    job_title_short
FROM 
    job_postings_fact
```
This above query will return the unique values from the column jon_title_short from the table job_postings_fact

`A semicolon (;) indicates the end of the SQL statement`

## WHERE

- This keyword sets a condition for the query
- The where statement is usually directly after the from statement

```
SELECT  
    job_title_short,
    job_location,
    job_via,
    salary_year_avg
FROM
    job_postings_fact
WHERE
    job_tite_short ='Data Analyst' (salary_year_avg > 9000)

```

## How to add comments?

-- Single line comment (two dashes)
/* Multi line comment */ 

- Helps make the query more readable
- To document the query

## ORDER BY

This keyword is used to sort the rows

- Default order: Ascending (smallest -> largest or A->Z), to get it in descending order write `ORDER BY column name DESC`
- `NULL` is the smallest if no values

Example:

```
SELECT  
    job_title_short,
    job_location,
    job_via,
    salary_year_avg
FROM
    job_postings_fact
WHERE
	job_title_short = 'Data Analyst'
ORDER BY
	salary_year_avg DESC
```

## Order to write commands

```
SELECT column1, column2
FROM table_name
WHERE condition
GROUP BY column
HAVING condition
ORDER BY column1 (ASC | DESC)
LIMIT number;
```