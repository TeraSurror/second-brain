- A Common Table Expression is a temporary result set that can be referenced from another SQL query

Syntax:
```
WITH cte_name (column_list) AS (
	CTE_query_definition
)
statement;
```

Example:
```postgresql
WITH cte_film AS (
	SELECT
		film_name,
		CASE (
			WHEN film_length < 30 THEN 'short'
			WHEN film_length >= 30 THEN 'medium'
			WHEN film_length >= 90 THEN 'long'
		END) length
	FROM films
)
SELECT film_name FROM cte_film WHERE length = 'medium';
```

