Make sure you download the starter code and run the following:

```sh
  psql < movies.sql
  psql movies_db
```

In markdown, you can place a code block inside of three backticks (```) followed by the syntax highlighting you want, for example

\```sql

SELECT \* FROM users;

\```

Using the `movies_db` database, write the correct SQL queries for each of these tasks:

1.  The title of every movie.
SELECT title FROM movies;
2.  All information on the G-rated movies.
SELECT rating FROM movies;
3.  The title and release year of every movie, ordered with the
    oldest movie first.
SELECT title,release_year FROM movies ORDER BY release_year;
4.  All information on the 5 longest movies.
SELECT * FROM movies ORDER BY runtime DESC LIMIT 5;
5.  A query that returns the columns of `rating` and `total`, tabulating the
    total number of G, PG, PG-13, and R-rated movies.
SELECT rating, COUNT(*) AS total FROM movies WHERE rating IN ('G','PG','PG-13','R') GROUP BY rating ORDER BY rating;
6.  A table with columns of `release_year` and `average_runtime`,
    tabulating the average runtime by year for every movie in the database. The data should be in reverse chronological order (i.e. the most recent year should be first).
SELECT release_year, AVG(runtime) AS average_runtime FROM movies GROUP BY release_year ORDER BY release_year DESC;
7.  The movie title and studio name for every movie in the
    database.
SELECT title, studio_id FROM movies
8.  The star first name, star last name, and movie title for every
    matching movie and star pair in the database.
SELECT stars.first_name, stars.last_name, movies.title
FROM stars
INNER JOIN movies ON stars.id = movies.id;

9.  The first and last names of every star who has been in a G-rated movie. The first and last name should appear only once for each star, even if they are in several G-rated movies. *IMPORTANT NOTE*: it's possible that there can be two *different* actors with the same name, so make sure your solution accounts for that.
SELECT stars.first_name, stars.last_name
FROM stars
INNER JOIN movies ON stars.id = movies.id
WHERE movies.rating = 'G'
10. The first and last names of every star along with the number
    of movies they have been in, in descending order by the number of movies. (Similar to #9, make sure
    that two different actors with the same name are considered separately).
SELECT stars.first_name, stars.last_name, COUNT(movies.title) AS movie_count
FROM stars
INNER JOIN movies ON stars.id = movies.id
GROUP BY stars.id, stars.first_name, stars.last_name
ORDER BY  movie_count DESC;
### The rest of these are bonuses

11. The title of every movie along with the number of stars in
    that movie, in descending order by the number of stars.
SELECT movies.title, COUNT(stars.id) as star_count
FROM stars
INNER JOIN movies ON movies.id = stars.id
GROUP BY movies.id, movies.title
ORDER BY star_count DESC;
12. The first name, last name, and average runtime of the five
    stars whose movies have the longest average.
SELECT stars.first_name, stars.last_name, AVG(movies.runtime) AS avg_runtime
FROM stars
INNER JOIN movies ON stars.id = movies.id
GROUP BY stars.id, stars.first_name, stars.last_name
ORDER BY avg_runtime DESC
LIMIT 5
13. The first name, last name, and average runtime of the five
    stars whose movies have the longest average, among stars who have more than one movie in the database.
SELECT stars.first_name,stars.last_name,AVG(movies.runtime)
FROM stars
INNER JOIN movies ON stars.id = movies.id
ORDER BY stars.id,stars.first_name, stars.last_name
WHERE (movies.id) > 1
ORDER BY movies.runtime DESC
limit 5;

14. The titles of all movies that don't feature any stars in our
    database.
SELECT movies.title
FROM movies 
LEFT JOIN movie.id ON
WHERE movie.d IS NULL
.
