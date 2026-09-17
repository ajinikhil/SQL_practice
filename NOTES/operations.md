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