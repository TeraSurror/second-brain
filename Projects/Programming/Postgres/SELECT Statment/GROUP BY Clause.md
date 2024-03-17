Syntax:
```
SELECT
	column1,
	column2,
	AGGREGATE_FUNCTION(column3), ...
FROM
	table
GROUP_BY
	column1,
	column2,...
HAVING
	condition
```

Example:
```postgresql
SELECT
	customer_id,
	SUM (amount) as total_amount
FROM
	payment
GROUP BY
	customer_id
HAVING
	SUM(amount) >= 1000
ORDER BY
	total_amount DESC;
```

