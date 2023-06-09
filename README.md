## Module 22 Report - Home_Sales.

## Overview.

## The purpose of this challenge is to use our knowledge of SparkSQL to determine key metrics about home sales data. I used Spark to create temporary views, partitioned the data, cached and uncached a temporary table, and verified that the table had been uncached.

<Home_Sales_colab.ipynb> 

## Results

A Spark DataFrame was created from the dataset. 
 - A column was added for year_sold from date column.

 - Question 2 - A temporary table called home_sales created.
 - Question 3 - Returned the average price, rounded to two decimal places, for a four-bedroom house that was sold in each year.
 - Question 4 - Returned the average price, rounded to two decimal places, of a home that has three bedrooms and three bathrooms, for each year built. 
 - Question 5 - Returned the average price of a home with three bedrooms, three bathrooms, two floors, and is greater than or equal to 2,000 square feet for each year built, rounded to two decimal places.

 - Question 6 - Returned the view rating for the average price for homes that are greater than or equal to $350,000, rounded to two decimal places. 
 - The run time for this query was 0.91.
 - Question 7 & 8 - The "home_sales" temporary table was cached and validated. 
 - Question 9 - The query from question 6 was run on the cached temporary table, and the run time computed for this query was much quicker and was 0.67.
 - Question 10 & 11 - A partition of the home sales dataset by the "date_built" field was created, and the formatted parquet data was read.
 - Question 12 - A temporary table of the parquet and partitioned data was created.
 - Question 13 - The query from question 6 was run on the parquet and partitioned temporary table, and was 0.58.
 - Question 14 & 15 - The "home_sales" temporary table was uncached and verified.

There was some debate about how to comprehend question 6.
Bootcamp spot had: What is the "view" rating for homes costing more than or equal to $350,000?
The notebook had: What is the "view" rating for the average price of a home, rounded to two decimal places, where the homes are greater than or equal to $350,000? 

So I hope my interpretation was correct.
I understood it to be what is the average price of a home for each view rating, where homes are greater than or equal to $350,000. Hence one could determine if increasing views may have increased average prices of home sales.

As I was unsure I repeated question 6-15 with the bootcamp spot question with the following run times.

 - Question 6 - The run time for this query was 0.67.
 - The cached temporary table, and the run time computed for this query was 0.22.
 - The run time computed for the parquet and partitioned temporary table was 0.43.

## Summary.

When comparing the run time on a query of home-sales (Question 6-15) on the temporay table created the cached table query was quicker. One would expect this to occur with the data being loaded from computer memory rather than from distributed nodes.

The parquet and partitioned, on "date_built" column, was loaded across more distributed nodes and generated an even quicker run time for the query.

### Enjoy marking! Sandra