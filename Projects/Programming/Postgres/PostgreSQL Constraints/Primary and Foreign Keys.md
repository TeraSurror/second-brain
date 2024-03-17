
### Primary Keys

- Column or a group of columns that uniquely identify a row in the table.
- It can be thought of as a combination between NOT NULL and UNIQUE constraint.

Syntax:
```
CREATE TABLE table_name (
	identifier_column PRIMARY KEY,
	...
)
```


### Foreign Keys

- A column or a group of columns that reference the primary key of another table.
- It helps maintain referential integrity among parent and child tables.
Syntax
```
FOREIGN KEY (column_name_current_table)
	REFERENCES parent_table(column_name_parent_table)
```

