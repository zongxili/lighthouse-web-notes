# PostgreSQL

Already having PostgreSQL in VM
May need update the Operating System / Vetual Machine often and check to make the command line interface is kenda working well.

Type `psql` to enter into the Database
`\c database_name` to connect the database, users have to enter every time when they enter in to a new `psql` section;

`;` make command execute.

Date can do comparison as well, `>` means after the date and `<` means before that date.

The command like "SELECT" can be **Case-Insensitive**, but the Value like "Paul" must be **Case-Sensitive**.

The max value of `VARCHAR` is `VARCHAR(255)`.

##### DELETE CASCADE:
`ON DELETE CASCADE`
- "A foreign key with cascade delete means that if a record in the parent table is deleted, then the corresponding records in the child table will automatically be deleted. This is called a cascade delete in Oracle."


##### Difference between `TEXT` and `VARCHAR(SIZE)`
- They all have the max length of 65535 characters
  - But `TEXT` can not be set;
- `VARCHAR(SIZE)` can be part of **`INDEX`** but the another one can not.

##### Having VS Where

- "`WHERE` clause introduces a condition on individual rows; `HAVING` clause introduces a **condition on aggregations**, i.e. results of selection where a single result, such as **count, average, min, max, or sum**, has been produced from multiple rows. Your query calls for a second kind of condition (i.e. a condition on an aggregation) hence `HAVING` works correctly."

- "As a rule of thumb, use `WHERE` before `GROUP BY` and HAVING after `GROUP BY`. It is a rather primitive rule, but it is useful in more than 90% of the cases."

##### DATE data Types
- "The format of a **TIMESTAMP** column is **YYYY-MM-DD HH:MM:SS** which is fixed at 19 characters. The TIMESTAMP value has a **range** from '1970-01-01 00:00:01' UTC to '2038-01-19 03:14:07' UTC"
- **TIME** range: "00:00:00.0000000 through 23:59:59.9999999 (00:00:00.000 through 23:59:59.999)"

In General:
- DATE - format YYYY-MM-DD.
- DATETIME - format: YYYY-MM-DD HH:MI:SS.
- TIMESTAMP - format: YYYY-MM-DD HH:MI:SS.
- YEAR - format YYYY or YY.


##### `FROM` sub select table
```sql
SELECT * FROM (
  SELECT something_id
  FROM someTable
  WHERE something
) as sub_table;
```


##### aggregate function calls cannot be nested
- That is, we cannot have one Aggregate Function is **Wrapped by** another one, this is a common misake people may have.
- In this case, we may need to use a **nesting / sub** query.

For example: 
```sql
SELECT count(sum(completed_at - started_at)) as average_total_duration
```
This is strictly prohibited by the Compiler.

##### Get the TOP 1 from the list
```sql
LIMIT 1;
```
This allows any result --> numbers / strings / etc...


##### `IN`
- Sub queries case: Dealing results with multi data;
- Hard code data: can have a statement like:
```sql
SELECT * 
FROM Something
WHERE type in (1, 2, 3);
```

#### Some notable examples:
Count people in a row:
```sql
SELECT count(*) FROM row_name;
```

if we want add a primary key named id and the id field is auto-incremented by one, we use the following statement:
```sql
id SERIAL PRIMARY KEY,
```

Check the **NULL** need to use the **IS**
```sql
WHERE column_name IS NULL;
```

Use **AND** to add more conditions in `WHERE`
```sql
WHERE condition1 AND condition2 AND condition3 ...;
```

Check if people don't have a Gmail as they emails, the **%** is used here.
```
WHERE email NOT LIKE '%@gmail.com'
```

Setting Default values
```sql
City varchar(255) DEFAULT 'Sandnes'
```


This is super tricky here: **AS total_duration** has to be added after the second `SELECT` (thats the tricky part) also after entire `FROM` statement (and this is SQL syntex).
```sql
SELECT avg (total_duration) AS average_total_duration
FROM (
  SELECT sum(completed_at - started_at) as total_duration
  FROM assistance_requests
  JOIN students ON students.id = assistance_requests.student_id
  JOIN cohorts ON cohorts.id = cohort_id
  GROUP BY cohorts.name
) AS total_duration;
```