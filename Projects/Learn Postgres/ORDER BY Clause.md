
##### ORDER BY CLAUSE
syntax: 
```
SELECT 
	expression 
FROM 
	table 
ORDER BY 
	column_name_1 ASC/DESC, 
	column_name_2 ASC/DESC;
```

We can also use aliases to query:
```
SELECT 
	first_name,
	LENGTH(first_name) as len
FROM 
	customers 
ORDER BY
	len DESC;
```

We can also specify if we want to print the nulls at the end or not:
```
SELECT * FROM customers ORDER BY NULLS LAST/FIRST;
# NULLS FIRST is default
```

