# Database design

Database is collection of tables.

- www.draw.io : a great tool to do ERD

**Try not to DELETE ANYTHING**

- Use `active` BOOLEAN flag: incase the Users want recover the data;

If we have **similar tables**: making types attribute instead of having different tabels;

The unique thing will stay at their own tables

#### Table names
- need check ANDY notes
- Use snake_case for table and column names.
- Pluralize tables names, column names should be singular.
- Call your primary key id.
- For most foreign keys use <table>_id.

#### One to many

- The foreign key should be stored in the **Many** side;
- Since the key will be repeated for so many times...

---

#### Many to Many 

##### Repeating Groups / Columns
- For example, we have Authers table & Books table, a Book can be **coauthored** by different people, and then we may need 2 columns for authors, or 2 authors in the same column, and they are **BAD ideas**.
- Instead, we can have another table: author_table, this **combine** 2 tables. This includes its own ID, AuthorID and TitleID.






---
#### Snake case
- (or snake_case) is the practice of writing compound words or phrases in which the elements are separated with one underscore character (_) and no spaces.

#### Need to know
- signed and unsigned in math
- Referential Integrity