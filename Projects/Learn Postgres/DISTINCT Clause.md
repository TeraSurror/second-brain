Syntax:
```
SELECT 
	DISTINCT column_name
FROM
	table;
```

we can use DISTINCT ON (expression) to keep the "first" row of duplicates
```
SELECT 
	DISTINCT ON (column_name/expression) as column_alias
FROM
	table
ORDER BY
	column_alias;
```