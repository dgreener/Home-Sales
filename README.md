# Home-Sales Challenge ReadMe
We used SparkSQL to analyze home sales data. This was used to answer the following questions. 
In addition, we show that cached and parquet data have faster runtimes that the original non-chached, non-parquet data.

**1) What is the average price for a four-bedroom house sold for each year? Round off your answer to two decimal places.**
+--------------------+----------+
|round(avg(price), 2)|year(date)|
+--------------------+----------+
|           296363.88|      2022|
|           301819.44|      2021|
|           298353.78|      2020|
|            300263.7|      2019|
+--------------------+----------+

**2) What is the average price of a home for each year it was built that has three bedrooms and three bathrooms? Round off your answer to two decimal places.**
+--------------------+----------------+
|round(avg(price), 2)|year(date_built)|
+--------------------+----------------+
|           292676.79|            2017|
|           290555.07|            2016|
|            288770.3|            2015|
|           290852.27|            2014|
|           295962.27|            2013|
|           293683.19|            2012|
|           291117.47|            2011|
|           292859.62|            2010|

**3) What is the average price of a home for each year that has three bedrooms, three bathrooms, two floors, and is greater than or equal to 2,000 square feet? Round off your answer to two decimal places.**
+--------------------+----------------+
|round(avg(price), 2)|year(date_built)|
+--------------------+----------------+
|           280317.58|            2017|
|            293965.1|            2016|
|           297609.97|            2015|
|           298264.72|            2014|
|           303676.79|            2013|
|           307539.97|            2012|
|           276553.81|            2011|
|           285010.22|            2010|
+--------------------+----------------+

**4) What is the "view" rating for homes costing more than or equal to $350,000? Determine the run time for this query, and round off your answer to two decimal places.**
+----+-------------+
|VIEW|AVERAGE_PRICE|
+----+-------------+
|  99|   1061201.42|
|  98|   1053739.33|
|  97|   1129040.15|
|  96|   1017815.92|
|  95|    1054325.6|
|  94|    1033536.2|
|  93|   1026006.06|
|  92|    970402.55|
|  91|   1137372.73|
|  90|   1062654.16|
|  89|   1107839.15|
|  88|   1031719.35|
|  87|    1072285.2|
|  86|   1070444.25|
|  85|   1056336.74|
|  84|   1117233.13|
|  83|   1033965.93|
|  82|    1063498.0|
|  81|   1053472.79|
|  80|    991767.38|
+----+-------------+
only showing top 20 rows

--- 1.515763282775879 seconds ---

**5) Using the cached data, run the query that filters out the view ratings with an average price of greater than or equal to $350,000. 
Determine the runtime and compare it to uncached runtime. Partition by the "date_built" field on the formatted parquet home sales data.**
+----+-------------+
|  99|   1061201.42|
|  98|   1053739.33|
|  97|   1129040.15|
|  96|   1017815.92|
|  95|    1054325.6|
|  94|    1033536.2|
|  93|   1026006.06|
|  92|    970402.55|
|  91|   1137372.73|
|  90|   1062654.16|
|  89|   1107839.15|
|  88|   1031719.35|
|  87|    1072285.2|
|  86|   1070444.25|
|  85|   1056336.74|
|  84|   1117233.13|
|  83|   1033965.93|
|  82|    1063498.0|
|  81|   1053472.79|
|  80|    991767.38|
+----+-------------+
only showing top 20 rows

--- 0.5178549289703369 seconds ---

**Parquet Data**
+----+-------------+
|VIEW|AVERAGE_PRICE|
+----+-------------+
|  99|   1061201.42|
|  98|   1053739.33|
|  97|   1129040.15|
|  96|   1017815.92|
|  95|    1054325.6|
|  94|    1033536.2|
|  93|   1026006.06|
|  92|    970402.55|
|  91|   1137372.73|
|  90|   1062654.16|
|  89|   1107839.15|
|  88|   1031719.35|
|  87|    1072285.2|
|  86|   1070444.25|
|  85|   1056336.74|
|  84|   1117233.13|
|  83|   1033965.93|
|  82|    1063498.0|
|  81|   1053472.79|
|  80|    991767.38|
+----+-------------+
only showing top 20 rows

--- 0.5889675617218018 seconds ---





