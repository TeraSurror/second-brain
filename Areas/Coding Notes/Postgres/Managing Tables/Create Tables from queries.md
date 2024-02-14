### SELECT INTO

Syntax:
```postgresql
SELECT INTO TABLE table_name
FROM another_table_name
WHERE some_condition -- this can be any clause like inner join and so on
```

This creates a new table from the contents of an existing table

Example:
```postgresql
SELECT INTO TABLE highly_rated_film
FROM film
WHERE film_rating >= 3;
```

### CREATE TABLE AS

Syntax:
```postgresql
CREATE TABLE table_name (column_list)
AS query
```

Example:
```postgresql
CREATE TABLE action_films (film_id, film_name)
AS
SELECT film_id, film_name FROM films WHERE film_genre = 'ACTION';
```

