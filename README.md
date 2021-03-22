# Sales Insights Data Analysis Project

## Data Analysis Using SQL

1. Show all purchase of liquor in the State of Iowa
```
SELECT * FROM `bigquery-public-data.iowa_liquor_sales.sales` ;
```
  
2. Show total number of purchase of liquor in the State of Iowa
```
SELECT COUNT(*) FROM `bigquery-public-data.iowa_liquor_sales.sales`;

```
3. Show distinct category name of liquor that purchase by Mississippi River Distillery (store number for Mississippi River Distillery is 9002)
```
SELECT DISTINCT category_name FROM `bigquery-public-data.iowa_liquor_sales.sales` WHERE store_number = '9002';

```
4. Show total number of bottles sold in pack 12
```
SELECT store_name, city, bottles_sold FROM `bigquery-public-data.iowa_liquor_sales.sales` WHERE pack = 12 AND bottles_sold > 1000 ORDER BY bottles_sold DESC;
```
