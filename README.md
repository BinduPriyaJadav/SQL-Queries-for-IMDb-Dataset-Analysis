# SQL-Queries-for-IMDb-Dataset-Analysis
Get top-rated movies:
SELECT movie_title, AVG(rating) AS average_rating
FROM movies
JOIN ratings ON movies.movie_id = ratings.movie_id
GROUP BY movie_title
ORDER BY average_rating DESC
LIMIT 10;
Most popular actors:

sql
Copy
Edit
SELECT actor_name, COUNT(movie_id) AS number_of_movies
FROM actors
JOIN movie_cast ON actors.actor_id = movie_cast.actor_id
GROUP BY actor_name
ORDER BY number_of_movies DESC
LIMIT 10;
Movies per genre:

sql
Copy
Edit
SELECT genre, COUNT(movie_id) AS movie_count
FROM movies
GROUP BY genre
ORDER BY movie_count DESC;
Average rating per genre:

sql
Copy
Edit
SELECT genre, AVG(rating) AS average_rating
FROM movies
JOIN ratings ON movies.movie_id = ratings.movie_id
GROUP BY genre
ORDER BY average_rating DESC;
Movies released each year:

sql
Copy
Edit
SELECT release_year, COUNT(movie_id) AS movies_count
FROM movies
GROUP BY release_year
ORDER BY release_year DESC;
