# Trends-in-StartUps
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

#9. 
