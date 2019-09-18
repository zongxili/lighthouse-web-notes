# SQL from our Apps



## Steps in the Lecture

- Make a database
- Make new folder and do **npm inil** in it
  - This will make a pachage.json and some files \
- Design the tables
- Inside the folder above, make a SQL folder
- Make a **pokemon.sql** file
  - first line somthing like this for every table
    - ```sql
      DROP TABLE pokemons IF EXISTS;
      ```
- do ```\i``` to add tables

#### Server side
- Just normal step:
  - create a server 
  - require the ```body-praser```
  - Yes we will get the data from **body**
- add a line in ```script```
  - add a **start : node index.js**
- Do **npm start**
- make a db which requires a js file and get connection from it
  - In that js file:
- have a **.env** file
  - do the ```require``` line for the environment variables
- make a **dataHelpers**: a brunch of functions we will use in the pokemon
  - can do exports those functions back to **index.js** file
  - One imp point here: **dont have the access to db**
  - look at the code


## SQL Injection
- SQL injection is a code injection technique that might **destroy** your database.
- SQL injection is one of the most common web hacking techniques.
- SQL injection is the placement of malicious code in SQL statements, via web page input.

#### NEED TO KNOW
- [MongoDB](https://en.wikipedia.org/wiki/MongoDB)
- NPM init
- pg
- express route
- debugger: this needs to be treat seriously!!
- [Postman](https://www.getpostman.com)