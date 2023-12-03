Inner join on table with itself:
```postgresql
SELECT column_names
FROM 
	some_table t1 INNER JOIN some_table t2
ON join_predicate
```


Left join on table with itself:
```postgresql
SELECT column_names
FROM 
	some_table t1 LEFT JOIN some_table t2
ON join_predicate
```


Right join on table with itself:
```postgresql
SELECT column_names
FROM 
	some_table t1 RIGHT JOIN some_table t2
ON join_predicate
```