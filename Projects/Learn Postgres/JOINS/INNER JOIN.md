Consider 2 tables like this:

| table_a |
|---------|
|pka      |
|column_1 |
|column_2 |

| table_b |
|---------|
|fka      |
|column_1 |
|column_2 |

table_a has a column **pka** that matches with a column **fka** with table_b.
To combine the table on those values we use the following syntax:

```postgresql
SELECT a.pka, b.fka, a.column_1, b.column_1
FROM table_a a INNER JOIN table_b b
ON a.pka = b.fka;
```

Note:
LEFT JOIN and RIGHT JOIN work in the same way, just replace INNER with RIGHT OR LEFT, depending on what you want.
