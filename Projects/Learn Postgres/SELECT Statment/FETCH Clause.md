Syntax:
```
OFFSET start {ROW | ROWS}
FETCH { FIRST | NEXT } row_count { ROW | ROWS } ONLY
```

1. ROW and ROWS are inter-changeable
2. FIRST and NEXT are inter-changeable
3. start is the number of rows to skip

Eg.
```postgresql
SELECT film_id, title
FROM film
ORDER BY title
OFFSET 5 ROWS
FETCH FIRST 5 ROWS;
```
