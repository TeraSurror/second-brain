Syntax:
```
WITH RECURSIVE cte_name AS (
	cte_query_definition_1 // non-recursive term
	UNION [ALL]
	cte_query_definition_2 // recusive term
)
SELECT * FROM cte_name;
```

Example:
```postgresql
WITH RECURSIVE subordinates AS (
	SELECT
		employee_id,
		manager_id,
		full_name
	FROM
		employees
	WHERE
		employee_id = 2
	UNION
		SELECT
			e.employee_id,
			e.manager_id,
			e.full_name
		FROM
			employees e
		INNER JOIN subordinates s ON s.employee_id = e.manager_id
) SELECT
	*
FROM
	subordinates;
```

For explanation check out this link: https://www.postgresqltutorial.com/postgresql-tutorial/postgresql-recursive-query/