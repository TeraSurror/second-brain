Syntax:
```
SELECT 
	column_names/expression
FROM
	table
WHERE 
	condition
ORDER BY (optional)
	column_names/column_aliases
```

**Since WHERE is evaluated before SELECT, we cannot use aliases in WHERE conditions**

Some conditional operators:
1. LIKE
2. IN
3. BETWEEN
4. AND
5. OR
6. IS NULL
7. NOT