# Trends-in-StartUps Aggregate Functions
This is one of the projects from the course I completed on Codecademy
*Howdy! It’s your first day as a TechCrunch reporter. Your first task is to write an article on the rising trends in the startup world.
To get you started with your research, your boss emailed you a project.sqlite file that contains a table called startups. It is a portfolio of some of the biggest names in the industry.
Write queries with aggregate functions to retrieve some interesting insights about these companies.*

#1. Getting started by taking a look at the 'startups' table
SELECT *
FROM startups;

#2. Calculating the total number of companies in the table
SELECT COUNT(*)
FROM startups;

#3. We want to know the total value of all companies in this table
SELECT SUM (valuation)
FROM startups;

#4. What is the highest amount 'raised' by a startup?
SELECT MAX(raised)
FROM startups;

#5. Edit the query so that it returns the maximum amount of money 'raised', during "Seed" stage.
SELECT MAX(raised)
FROM startups
WHERE stage = 'Seed';

#6. In what year was the oldest company on the list founded?
SELECT MAX(founded)
FROM startups;

#7. Return the average 'valuation'
SELECT AVG(valuation)
FROM startups;

#8. Return the average 'valuation' in each 'category'
SELECT category, AVG(valuation)
FROM startups
GROUP BY category;

#9. Return the average 'valuation' in each 'category' and round the average to two decimal places.
SELECT category, ROUND(AVG(valuation), 2)
FROM startups
GROUP BY category;

#10. Return the average 'valuation' in each 'category' and round the average to two decimal places. Lastly, order the list from highest averages to lowest
SELECT category, ROUND(AVG(valuation), 2)
FROM startups
GROUP BY 1
ORDER BY 2 DESC;

#11. What are the most competitive markets? First, return the name of each 'category' with the total number of companies that belong to it
SELECT category, COUNT (*)
FROM startups
GROUP BY category;

#12. Next, we filter the results to only include categories that have more than 3 companies in them
SELECT category, COUNT (*)
FROM startups
GROUP BY category
HAVING COUNT(*) > 3;

#13. Let's see if theres a difference in startup sizes among different locations: 
What is the average size of a startup in each location?
SELECT  location, AVG(employees)
FROM startups
GROUP BY location;

#14. What is the average size of a startup in each 'location', with average sizes above 500?
SELECT  location, AVG(employees)
FROM startups
GROUP BY location
HAVING AVG(employees) > 500;
