__Wildcards are used to substitute one or more characters in a string__

    * Wildcards are used with the `LIKE` operator
    * All of this (i.e., `LIKE`, `%`, and `_`) is used in the where clause

## %

- % represents zero, one , or more characters

#### Example 1:

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
	job_title LIKE '%Analyst%'
```

___The above example will return job titles that have the word `Analysts`___

#### Example 2:

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
	job_title LIKE '%Analyst'
```

___Example 2 will return the job posting that ends with the word `Analyst`___

#### Example 3:

```
SELECT 
	job_id,
    job_title,
    job_location,
    job_via,
    salary_year_avg
FROM
	job_postings_fact
WHERE
	job_title LIKE 'Analyst%'
```

___Example 3 will return job postings that start with the word `Analyst`___

#### Example 4:

```
SELECT 
	job_id,
    job_title,
    job_location,
    job_via,
    salary_year_avg
FROM
	job_postings_fact
WHERE
	job_title LIKE 'Business%Analyst%'
```

___Example 4 returns job titles that have the words `Business` and `Analysts` in them___

## `_`

- `_` represents one single character

#### Example 1:

```
SELECT 
	job_id,
    job_title,
    job_location,
    job_via,
    salary_year_avg
FROM
	job_postings_fact
WHERE
	job_title LIKE '%Business_Analyst%'
```

___Example 1 will return job titles with the words Business Analysts including the jobs that has words before and after the words `Business Analysts`___