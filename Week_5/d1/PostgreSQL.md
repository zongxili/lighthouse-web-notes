# PostgreSQL

Already having PostgreSQL in VM
May need update the Operating System / Vetual Machine often and check to make the command line interface is kenda working well.

Type `psql` to enter into the Database
`\c database_name` to connect the database, users have to enter every time when they enter in to a new `psql` section;

`;` make command execute.

Date can do comparison as well, `>` means after the date and `<` means before that date.

The command like "SELECT" can be **Case-Insensitive**, but the Value like "Paul" must be **Case-Sensitive**.

The max value of `VARCHAR` is `VARCHAR(255)`.

`ON DELETE CASCADE`:
"A foreign key with cascade delete means that if a record in the parent table is deleted, then the corresponding records in the child table will automatically be deleted. This is called a cascade delete in Oracle."


Difference between `TEXT` and `VARCHAR(SIZE)`
- They all have the max length of 65535 characters
  - But `TEXT` can not be set;
- `VARCHAR(SIZE)` can be part of **`INDEX`** but the another one can not.

#### Some notable examples:
Count people in a row:
```SELECT count(*) FROM row_name;```

if we want add a primary key named id and the id field is auto-incremented by one, we use the following statement:
```id SERIAL PRIMARY KEY,```

Check the **NULL** need to use the **IS**
`WHERE column_name IS NULL;`

Use **AND** to add more conditions in `WHERE`
`WHERE condition1 AND condition2 AND condition3 ...;`

Check if people don't have a Gmail as they emails, the **%** is used here.
`WHERE email NOT LIKE '%@gmail.com'`

