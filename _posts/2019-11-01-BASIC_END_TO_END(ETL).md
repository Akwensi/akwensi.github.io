---
title: "End to end ETL"
date: 2019-11-14
tags: [batch processing, transform, spark, pyspark, data mining, ngrams, bigrams trigrams]
header:
  image: "/end to end.png"
excerpt: "Data engineering, Data Science, ngrams, trigrams"
mathjax: "true"
---

# End To End ETL

In this project we worked with a relational database to extract data across different tables by connecing the databases directly thus End To End ETL.

Here is the [link](https://github.com/Akwensi/BASIC-END-TO-END-ETL-PIPELINE-_project3)? to the **Jupiter Notebook** and **SQL** scripts generated in this project.  

The main technologies used in this project were:
    1. Aparche PySpark
    2. PostgreSQL
    3. DBeaver

The project is segregated into several sections with the appropriate instructions.

***Prior to executing of the instructions below;***
  a. Download "postgresql-42.2.8.jar" and place it in your project directory
  b. Install Postgres
  c. Install DBeaver
  d. Connect the DBeaver to the Postgres Database

  ## **Configuration task:**
### 1. DATA EXTRACTION:
      
Initialize spark with the following:

spark = (
    SparkSession.builder
                .appName("Stack Overflow Data Wrangling")
                .config("spark.jars", "C:\Users\USER\Desktop\Blossom_Academy\jars\postgresql-42.2.8.jar") 
                .getOrCreate()
)

i. appName: Is the name given to blah blah
ii. config("spark.jars", "C:\Users\USER\Desktop\Blossom_Academy\jars\postgresql-42.2.8.jar"): In spark, you may want to connect to databases directly and extract some data, instead of loading a file. You will need to add this extra configuration. This config is just enabling us to be able to read/write from/to a Postgres DB


Load the StackOverflow questions, answers and users datasets with pyspark
**HINT:** rename all id columns as you may encounter problems with multiple columns having the same name when you join several data frames.  Eg: Assuming you loaded the answers data into a variable called answers, rename this as follows,

**answers = answers.withColumnRenamed(‘id’, ‘answer_id’)** 


### B. DATA TRANSFORMATION:
Assuming you have a folder on your computer named Blossom_Academy, create a new folder within this folder called jars then place this file into it.


TASKS:
  1. Select users from only one country of your choosing.
  2. Extract the country and city into new columns.
  3. Join this with the questions and only pick questions with at least 20 view_counts.
  4. Join the answers to the results of (3).

NB: Choosing some countries will result in empty dataframes after completing task 4. Choose wisely


OPTIONAL:
In (py)spark, you can think of your dataframe as an SQL table(although distributed). You can write SQL queries within pyspark for instance. Assuming your dataframe is called df, Try the following:

[1] df.registerTempTable('new_df')
[2] spark.sql("SELECT col1, col2, from new_df").show()

There’s no performance gain/loss in using SparkSQL as opposed to using the python functions/methods. Spark SQL feels more elegant and easier for those already familiar with SQL.

Use this to return the minimum updated_at time.


3. DATA LOADING: *(to be executed in DBeaver)*

### SQL DATA DEFINITION LANGUAGE(DDL)
Create a new schema called stackoverflow_filtered.
Create one table called results. 


### DATA LOADING
*Use spark to write the results into this table with the snippet below.*
  1. Create a btree index on the reputation column within the results table.
  2. Create a hash index on the display_name column within the results table.
  3. From the results table, create a view with the column names display_name, city, questions_id where the accepted_answer_id is not null. Make sure this view goes into the right schema.
  4. Create a materialized view similar to (6). They should have different names.
  5. In your Jupyter notebook, state the difference between views and materialized views.



HINTS:
http://www.postgresqltutorial.com/postgresql-indexes/postgresql-create-index/
http://www.postgresqltutorial.com/managing-postgresql-views/
https://spin.atomicobject.com/2018/04/09/postgres-materialized-views/
	
NB: change the user=’postgres’ and password=‘Akwensi’ to what you used in your DB

df.write.format("jdbc").options(
    url='jdbc:postgresql://localhost/postgres',
    driver='org.postgresql.Driver',
    user='postgres',
    password='Akwensi',
    dbtable='stackoverflow_filtered.results'
).save(mode='append')


### 4. SQL DATA MANIPULATION LANGUAGE(DML)
  a. How many cities appeared more than twice in your results table?
  b. How many unique created_at dates(not datetime) are in the result table?
  c. If you were to give an award to one user, who will it be? And why?


EXPECTED RESULTS
    1. Save your python code in the jupyter notebook.
    2. Save the SQL code that was used to create the schema and table into an SQL script called ddl.sql 
    3. Save the SQL code that was used to answer the questions in section 4 into an SQL script called dml.sql
  Commit these 3 files into your private git repository.
