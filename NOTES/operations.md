## Arithmetic Operations

Arithmetic operations are used to perform mathematical calculations.

- `+` 
- `-` 
- `*`
- `/`
- `%`

### Example

```
SELECT 
	project_company,
    nerd_id,
    nerd_role,
    hours_rate AS rate_original,
    hours_rate - 5 AS rate_drop,
    hours_rate + 5 AS rate_hike
FROM
	invoices_fact
```

### Excample Locations Used

1. `SELECT` clause

    - For performing calculations on data retrieved from the database.
    - Excample: `SELECT salary, salary * 0.1 AS bonus FROM employees;`

2. `WHERE` CLAUSE

    - For filtering data based  on conditions that may involve arithmetic or logical operations.
    - example: `SELECT * FROM orders WHERE (quantity * unit_price) > 100;`