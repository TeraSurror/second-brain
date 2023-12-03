Syntax:
```
SELECT columns FROM table1
UNION
SELECT columns FROM table2
```

Combines rows from both select statements and removes duplicates provided:
1. The number and order of columns are the same
2. the data types of the columns are compatible

It also removes all duplicated. If you want duplicates, use UNION ALL

It does not order the results, so use ORDER BY to order the results

Example usage:
```postgresql
SELECT * FROM top_rated_movies
UNION
SELECT * FROM most_popular movies
ORDER BY title
```
