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

#### Some notable examples:
Count people in a row:
```SELECT count(*) FROM row_name;```

if we want add a primary key named id and the id field is auto-incremented by one, we use the following statement:
```id SERIAL PRIMARY KEY,```
