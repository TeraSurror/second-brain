- Query within a query
general syntax:
```
SELECT
	columns
FROM
	table1
WHERE
	some_condition (SUBQUERY -> SELECT * FROM some_table)
```

we can use the IN and EXISTS operators for conditions for the subquery
Eg: Find all movies whose rate is higher than the avg rate

```postgresql
SELECT film_name FROM films WHERE film_rate > (SELECT AVG(film_rate) FROM films)
```
