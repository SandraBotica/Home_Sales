## Module 22 Report - Home_Sales.

## Overview.

## The purpose of this challenge is to use our knowledge of SparkSQL to determine key metrics about home sales data. I used Spark to create temporary views, partition the data, cache and uncache a temporary table, and verify that the table has been uncached.

<Home_Sales_colab.ipynb> 

## Results

A Spark DataFrame was created from the dataset. 
 - A column was added for year_sold from date column.

A temporary table called home_sales created.

Queries written that:
 - Return the average price, rounded to two decimal places, for a four-bedroom house that was sold in each year.
 - Return the average price, rounded to two decimal places, of a home that has three bedrooms and three bathrooms. 
 - Return the average price of a home with three bedrooms, three bathrooms, two floors, and is greater than or equal to 2,000 square feet for each year built rounded to two decimal places.
 - Returns the view rating for the average price for homes that are greater than or equal to $350,000, rounded to two decimal places. 
 - The run time for this query was 1.48.

The "home_sales" temporary table was cached and validated. 
The last query above was run on the cached temporary table, and the run time computed for this query was much quicker and was 0.54.

A partition of the home sales dataset by the "date_built" field was created, and the formatted parquet data was read.
A temporary table of the parquet and partitioned data was created.
The query from above was run on the parquet and partitioned temporary table, and the run time computed for this query was slower then the cached data, but quicker than the first query, and was 0.97.

The "home_sales" temporary table was uncached and verified.

## Summary.


### Enjoy marking! Sandra