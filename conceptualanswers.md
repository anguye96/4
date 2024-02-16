### Conceptual Exercise

Answer the following questions below:

- What is PostgreSQL?
it is an open-source relational database 
- What is the difference between SQL and PostgreSQL?
PostgresSQL is open source and SQL is owned by microsoft and has limited support of database
- In `psql`, how do you connect to a database?
you need to know the name of your targetbase, the host name and port number of the server
- What is the difference between `HAVING` and `WHERE`?
WHERE selects input rows before groups, HAVING selects group rows after groups and aggregates are computed
- What is the difference between an `INNER` and `OUTER` join?
INNER joins result in overlapping part of two datasets, OUTER joins outer parts, exampling: for inner join, only the rows that both tables have in common returned, however outer join, all rows from both tables are returned
- What is the difference between a `LEFT OUTER` and `RIGHT OUTER` join?
LEFT OUTER join returns all the rows from the left table and the matched rows from the right table, same goes for RIGHT OUTER but returns all the rows from the right
- What is an ORM? What do they do?
is a piece of software designed to translate between the data representations used by database
- What are some differences between making HTTP requests using AJAX 
  and from the server side using a library like `requests`?
An ajax request is just an HTTP request made by javascript code, browsers load web pages by sending requests to the server using HTTP, each time a page loads, a request is made. javascript can do the same thing, but without needing to reload the whole page.
- What is CSRF? What is the purpose of the CSRF token?
is an attack that forces authenticated users to submit a request to a web application
- What is the purpose of `form.hidden_tag()`?
generates a hideen field that includes a token that is used to protect the form against CSRF attacks.