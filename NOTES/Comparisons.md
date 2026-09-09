# Comparisons
- it is used within teh `WHERE` or  `HAVING` clause 
- Used in conjunction with comparison operators:
    - =, <>, <, >, >=, <=
- used in conjunction with logical operators
    - AND, OR, BETWEEN, and IN

## <> / NOT(NOT equal to)

Example

```
SELECT 
	job_id,
    job_title_short,
    job_location,
    job_via,
    salary_year_avg
FROM
	job_postings_fact
WHERE
	job_via <> 'via Ai-Jobs.net'
```
OR

```
SELECT 
	job_id,
    job_title_short,
    job_location,
    job_via,
    salary_year_avg
FROM
	job_postings_fact
WHERE NOT
	job_via = 'via Ai-Jobs.net'
```

## `<` and `<=`

- < - less than
<= - less than or equal to

## `AND` operation

- When using this operation it will only shows records where all conditions are true
- Can have multiple `AND` conditions

example:

```
SELECT 
	job_id,
    job_title_short,
    job_location,
    job_via,
    salary_year_avg
FROM
	job_postings_fact
WHERE 
	salary_year_avg > 100000
    AND
	job_via = 'via Ai-Jobs.net'
```

## OR Operation

- OR operation is used when we want either one condition is true               
- A query can have multiple `OR` conditions

Example:

```
SELECT 
	job_id,
    job_title_short,
    job_location,
    job_via,
    salary_year_avg
FROM
	job_postings_fact
WHERE 
	job_title_short = 'Data Analyst'
    OR
    salary_year_avg > 100000
```

## BETWEEN

- The keyword `BETWEEN` gets the value within a given range
- Alternative to using AND, <=, >=

Example:

```
SELECT 
	job_id,
    job_title_short,
    job_location,
    job_via,
    salary_year_avg
FROM
	job_postings_fact
WHERE 
    salary_year_avg BETWEEN 100000 AND 200000
```

## IN

- The key word `IN` specify multipl;e values in a `WHERE` clause
- Alternative to using `OR` operator

Example:

```
SELECT 
	job_id,
    job_title_short,
    job_location,
    job_via,
    salary_year_avg
FROM
	job_postings_fact
WHERE 
	job_title_short IN ('Data Analyst', 'Data Engineer')
```
