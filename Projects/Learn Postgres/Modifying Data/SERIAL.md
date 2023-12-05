Syntax:
```postgresql
CREATE TABLE table_name (
	id SERIAL,
	...
)
```

This creates an auto-increment integer value. So if we insert another row in the table, the id column will automatically get updated.

By assigning the `SERIAL` pseudo-type to the `id` column, PostgreSQL performs the following:
- First, create a sequence object and set the next value generated by the sequence as the default value for the column.
- Second, add a `NOT NULL` constraint to the `id` column because a sequence always generates an integer, which is a non-null value.
- Third, assign the owner of the sequence to the `id` column; as a result, the sequence object is deleted when the `id` column or table is dropped

The above code is equivalent to the following code:
```postgresql
CREATE SEQUENCE table_name_id_seq;

CREATE TABLE table_name (
    id integer NOT NULL DEFAULT nextval('table_name_id_seq')
);

ALTER SEQUENCE table_name_id_seq
OWNED BY table_name.id;
```

To learn about sequences follow this link:
https://www.postgresqltutorial.com/postgresql-tutorial/postgresql-sequences/

#### GENERATED AS IDENTITY constraint

This is the SQL standard-conforming variant of SERIAL

Constraint is written as follows:
```postgresql
column_name type GENERATED {ALWAYS | BY DEFAULT } AS IDENTITY[ (sequence_option) ]
```

Example usage:
```postgresql
CREATE TABLE color (
	color_id INT GENERATED ALWAYS AS IDENTITY,
	color_name VARCHAR NOT NULL
);
```