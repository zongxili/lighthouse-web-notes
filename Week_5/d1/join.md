# JOINs in SQL

**Every JOIN must also have an ON.**

##### JOIN / INNER JOIN
- produces only the set of records that match in both Table A and Table B.

##### Full outer join
-  produces the set of all records in Table A and Table B, with matching records from both sides where available. If there is no match, the missing side will contain **null**.

##### Left outer join
- produces a complete set of records from Table A, with the matching records (where available) in Table B. If there is no match, the **right side** will contain null.

- exclude the records we don't want from the right side via a where clause.

```sql
SELECT * FROM TableA
LEFT OUTER JOIN TableB
ON TableA.name = TableB.name
WHERE TableB.id IS null
```