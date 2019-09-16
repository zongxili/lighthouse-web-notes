# PostgreSQL

Already having PostgreSQL in VM
May need update the Operating System / Vetual Machine often and check to make the command line interface is kenda working well.

Type `psql` to enter into the Database
`\c database_name` to connect the database;

`;` make command execute

Date can do comparison as well, `>` means after the date and `<` means before that date.

The command like "SELECT" can be **Case-Insensitive**, but the Value like "Paul" must be **Case-Sensitive**.

Count people in a row:
```SELECT count(*) FROM row_name;```

