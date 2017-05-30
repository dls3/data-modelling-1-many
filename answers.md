Find the author with the name 'Kara Melton' and then select all the articles she has written.

SELECT title FROM articles
WHERE author_id=(SELECT id FROM authors WHERE name ='Kara Melton');


Find Ontario in the provinces table and then find all the cities in that province.

SELECT name FROM cities
WHERE province_id=(SELECT id FROM provinces WHERE name='Ontario');

Who wrote the article called 'Coding Bootcamps and Emotional Labor'?

SELECT name FROM authors
WHERE id=(SELECT author_id FROM articles WHERE title='Coding Bootcamps and Emotional Labor');

Write a series of SQL queries to find out how many provinces are in Canada.

SELECT id FROM countries WHERE name='Canada';
SELECT name FROM provinces WHERE country_id=1;
SELECT count(name) FROM provinces WHERE country_id=1;


How many people live at 4740 McDermott Street?

SELECT count(name) FROM persons
WHERE residence_id=(SELECT id FROM residences WHERE address='4740 McDermott Street');

What city is 4740 McDermott Street in?

SELECT name FROM cities
WHERE id =(SELECT city_id FROM residences WHERE address='4740 McDermott Street');

What province is 4740 McDermott Street in?

SELECT name FROM provinces
WHERE id =(SELECT province_id FROM cities
WHERE id = (SELECT city_id FROM residences WHERE address='4740 McDermott Street'));

What country is 4740 McDermott Street in?

SELECT id FROM provinces
WHERE id =(SELECT province_id FROM cities
WHERE id = (SELECT city_id FROM residences WHERE address='4740 McDermott Street'));
SELECT name FROM countries where id=1;

Find the person named 'Destini Davis' and then use a series of SQL queries to find what country they live in.

Select id FROM residences WHERE id=(Select id FROM persons WHERE name='Destini Davis');
Select id FROM provinces WHERE id=(Select id FROM cities WHERE id=8);
Select name FROM countries WHERE id=1;


How many articles has Aditya Mukerjee written?

SELECT COUNT(id) FROM articles WHERE author_id=(SELECT id FROM authors WHERE name='Aditya Mukerjee');
