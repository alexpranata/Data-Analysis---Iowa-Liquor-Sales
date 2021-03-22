# Sales Insights Data Analysis Project

This dataset contains every wholesale purchase of liquor in the State of Iowa by retailers for sale to individuals since January 1, 2012.
This public dataset is hosted in Google BigQuery

https://console.cloud.google.com/marketplace/details/iowa-department-of-commerce/iowa-liquor-sales


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
4. Show total number of bottles sold in pack 12 and bottle sold greater than 1000
```
SELECT
  store_name,
  city,
  bottles_sold
FROM
  `bigquery-public-data.iowa_liquor_sales.sales`
WHERE
  pack = 12
  AND bottles_sold > 1000
ORDER BY
  bottles_sold DESC;
```

5. Show total sales of liquor that purchase by store
```
SELECT
  DISTINCT(store_name),
  SUM(sale_dollars) AS total_sales,
  SUM(bottles_sold) AS total_bottles_sold,
  MIN(bottles_sold) AS min_bottles_sold,
  MAX(bottles_sold) AS max_bottles_sold,
  AVG(bottles_sold) AS average_bottles_sold
FROM
  `bigquery-public-data.iowa_liquor_sales.sales`
GROUP BY
  store_name
ORDER BY
  total_sales DESC;
```
