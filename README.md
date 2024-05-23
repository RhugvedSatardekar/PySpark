
# PySpark DataFrame Operations README

This README provides a guide for various operations on PySpark DataFrames using code snippets.

## Installation

To use PySpark, install it using pip:

```python
!pip install pyspark
```

## Reading CSV Files

```python
from pyspark.sql import SparkSession

spark = SparkSession.builder.appName('DataFrame').getOrCreate()

# Reading CSV files
df_spark = spark.read.csv('test1.csv', header=True, inferSchema=True)
df_spark.show()
```

## Basic DataFrame Operations

```python
# Printing Schema
df_spark.printSchema()

# Descriptive Statistics
df_pyspark.describe().show()

# Adding Columns
df_pyspark = df_pyspark.withColumn('Experience After 2 years', df_pyspark['Experience'] + 1)

# Dropping Columns
df_pyspark = df_pyspark.drop('Experience After 2 years')

# Renaming Columns
df_pyspark = df_pyspark.withColumnRenamed('Name', 'New Name')

# Selecting Columns
df_pyspark.select('Name').show()

# Filtering Data
df_spark.filter((df_spark['Salary'] <= 20000) & (df_spark['Salary'] >= 15000)).select(['Name','Experience','Salary']).show()
```

## Missing Value Handling

```python
# Dropping Rows with Any Null Value
df_spark.dropna(how="any").show()

# Filling Missing Values
df_spark.na.fill('Missing Values', ['Name', 'age', 'Experience']).show()
```

## Grouping and Aggregation

```python
# Group By Name and Sum
df_spark.groupBy('Name').sum().show()

# Group By Department and Sum
df_spark.groupBy('Departments').sum().show()

# Mean Salary by Department
df_spark.groupBy('Departments').mean().show()

# Count by Department
df_spark.groupBy('Departments').count().show()

# Aggregating Salary
df_spark.agg({'Salary':'sum'}).show()

# Max Salary by Name
df_spark.groupBy('Name').max().show()
```

This README covers basic operations on PySpark DataFrames. For more detailed documentation, refer to official PySpark documentation.

## 🌐 Sources
1. [stackoverflow.com - Py4J error when creating a spark dataframe using pyspark](https://stackoverflow.com/questions/49063058/py4j-error-when-creating-a-spark-dataframe-using-pyspark)
2. [stackoverflow.com - Read csv using pyspark](https://stackoverflow.com/questions/48079611/read-csv-using-pyspark)
3. [stackoverflow.com - Load CSV file with PySpark](https://stackoverflow.com/questions/28782940/load-csv-file-with-pyspark)
4. [spark.apache.org - Installation — PySpark master documentation](https://spark.apache.org/docs/latest/api/python/getting_started/install.html)
5. [spark.apache.org - pyspark.sql.SparkSession.builder.getOrCreate](https://spark.apache.org/docs/3.1.3/api/python/reference/api/pyspark.sql.SparkSession.builder.getOrCreate)
6. [community.cloudera.com - how to read schema of csv file and according to column](https://community.cloudera.com/t5/Support-Questions/how-to-read-schema-of-csv-file-and-according-to-column/m-p/193863/highlight/true)
```
```
