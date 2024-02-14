Syntax:
```postgresql
CREATE TABLE table_name (
	column1 datatype(length) column_constraint,
	column2 datatype(length) column_constraint,
	column3 datatype(length) column_constraint,
	table_constraints
)
```

Following are the column constraints:
1. NOT NULL
2. UNIQUE
3. PRIMARY KEY
4. CHECK
5. FOREIGN KEY

Example:
```postgresql
CREATE TABLE account_roles (
  user_id INT NOT NULL,
  role_id INT NOT NULL,
  grant_date TIMESTAMP,
  PRIMARY KEY (user_id, role_id),
  FOREIGN KEY (role_id)
      REFERENCES roles (role_id),
  FOREIGN KEY (user_id)
      REFERENCES accounts (user_id)
);
```