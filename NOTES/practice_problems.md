## Problem 1
- Get job details for both 'Data Analyst' or 'Business Analyst' positions
    * For 'Data Anal;yst', get jobs which are  > $100k 
    * For 'Business Analyst', get jobs which are  > $70k

- Only include jobs located in either:
    * 'Boston, MA'
    * 'Anywhere (i.e., Remote Jobs)'

### Solution

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
	job_location IN ('Boston, MA', 'Anywhere') AND
    (
      (job_title_short = 'Data Analyst' AND salary_year_avg > 100000)	OR
      (job_title_short = 'Business Analyst' AND salary_year_avg > 70000)
    )
```

## Problem 2

- In the company_dim table find all company names that include 'Tech' immediately followed by any single character. Return the name column.

### Solution

```
SELECT 
	name
FROM
	company_dim
WHERE
	name LIKE '%Tech_'
```

## Problem 3

- Find all job postings in the job_postings_fact where the job_title is exactly "Engineer" and one character followed after the term. Get the job_id, job_title, and job_posted_date.

### Solution

```
SELECT 
	job_id,
    job_title,
    job_posted_date
FROM
	job_postings_fact
WHERE
	job_title LIKE 'Engineer_'
```

## Problem 4

- From the job_postings_fact return the following columns: job_id , job_title_short , job_location , job_via , job_posted_date , and salary_year_avg . Also, rename the following: job_via to job_posted_site and salary_year_avg to avg_yearly_salary .

### Solution

```
SELECT 
	salary_year_avg,
    job_title_short,
    job_location,
    job_via AS job_posted_site,
    job_posted_date,
    salary_year_avg AS avg_yearly_salary
FROM 
	job_postings_fact

```

## Problem 5

- Look for non-senior data analyst or business analyst roles
    - Only get job titles that include either 'Data' or 'Business'

    - Also include those with 'Analyst' in any part of the title

    - Don't include any job titles with 'Senior' followed by any character

- Get the job title, location, and average yearly salary

### Solution

```
SELECT 
	salary_year_avg AS salary,
    job_title,
    job_location AS location
FROM 
	job_postings_fact
    
WHERE 
	(job_title LIKE '%Data%' OR job_title LIKE '%Business%') AND
    job_title LIKE '%Analyst%'
AND
	job_title NOT LIKE '%Senior%'

```