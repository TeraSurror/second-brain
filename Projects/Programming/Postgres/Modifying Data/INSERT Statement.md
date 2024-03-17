Syntax:
```postgresql
INSERT INTO some_table (column1, column2, ...)
VALUES (value1, value2, ...)
```

It returns a command tag with the following form: `INSERT oid count`
1. `oid` is the object identifier used by postgres
2. count the number of rows inserted


If you omit required columns in the `INSERT` statement, PostgreSQL will issue an error. In case you omit an optional column, PostgreSQL will use the column default value for insert.

To insert multiple rows:
```postgresql
INSERT INTO some_table (column1, column2, ...)
VALUES 
	(value1, value2, value3, ...),
	(value1, value2, value3, ...),
	(value1, value2, value3, ...)
```

