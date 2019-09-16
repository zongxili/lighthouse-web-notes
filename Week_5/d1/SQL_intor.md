# SQL Intro lecture
store in memory in node:
Start with the command of node: read evaluate print loop
Once we exit the Node, we lost all data: jst like in console.

`irb`: enter to **Ruby**, enter `control + D` to exit

TinyApp, Tweeter: data was not _PERSISTENT_

Databse : externaml palce to store data; with CRUD

- also have some "smart" interaction: some specific actions, such as finding all "Zongxi"
- actully software to manage --> one notiable thing is, not only one person can write to the db;
- when connect to the db, actilly connect to server

Sending data from font end to back end

Sending HTTP requests which is layer in TCP: so also its TCP
such as Forms and a tag
- Adjx also js making XHR requests

back end send data to database:
just TCP connections, no HTTP

#### Two Database models:
- Relational Database Model
- Non-Relational database Model

#### The Language
- SQL: Structured Query Language;
  - All database speak the same language;
  - But different DB Server have different interface commands


`\`: means Postage commands
`\l`: list all DB;

`\dt`: show the names of all tables for Database connected to;

One termial can connect to only ONE database;



## NEED TO KNOW:
- psql connect with remote database;
- Can 2 machine connect to a DB at a same time?
- Different JOIN: INNER, OUTER, LEFT, RIGHT
- The Order of JOIN, ON, WHERE, GROUP BY, etc... NOT USING WHERE but AND
- AS: alias
- Nesting query
- Adding the floating point Number as percentage


[Converting VARCHAR numbers to NUMBER](https://stackoverflow.com/questions/18877047/tsql-conversion-from-varchar-to-numeric-works-for-all-but-integer)

"Actually there is no difference between the two. You can store string with single and double quotes. But... single quotes are used to indicate the beginning and end of a string in SQL. Double quotes generally aren't used in SQL, you use them in order to store lets say the whole SQL statement(query), in a variable so you can use it later in your code. As you correctly mention, yes you should stick to single quotes, in terms like when you want to indicate a string and not double. but you can do your job either way. Just another tip i can give you is that you should declare your tables and columns in lowercase. That way will be more convinient to you later when you use them inside your code. in PHP for example. Its easier to remember that you have all your fields in lowercase."


Boolean value: where proprerty = f OR where proprerty = 'false';