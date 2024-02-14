Syntax:
```postgresql
UPDATE some_table
SET 
	column1 = value1,
	column2 = value2,
	...
WHERE some_condition -- where clause is optional. If ommited; updates all rows
```

Returns a result tag in the form: `UPDATE count`
count is the number of rows updated


