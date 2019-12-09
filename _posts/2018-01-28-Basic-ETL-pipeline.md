---
title: "Basic ETL Project"
date: 2018-01-28
tags: [extract, transform, load data science, data]
header:
  image: "/images/data-engineering-2.jpeg.jpeg"
excerpt: "Data engineering, Data Science, Data"
mathjax: "true"
---

This project aimed at building a basic ETL pipeline to read data from a source (**AWS**), transform this data by doing some **aggregations** and then loading the output into a prescribed location ie s3 **bucket** on AWS

Here is the [link](https://github.com/Akwensi/Basic-ETL-pipeline-project1) to the **Jupiter Notebook** file used in the project.  

*Pandas* and *Amazon Simple Storage Service(S3)* are the main technologies used in this project.

The task is to:
    1. Write a python script with the following features; 
        a. Download the 7+ Million Dataset from S3 [bucket: blossom-data-engs key:-project1/free-7-million-company-dataset.zip].
        b. Read the file with pandas.
        c. Filter out companies without a domain name using pandas.
        d. Write out the output(from point c.) in the following formats 
            i. Parquet
            ii. JSON (compressed using gzip)
        e. Upload the resulting 3 file to your S3 buckets blossom-data-eng-[student-name].

    4.  Commit your code to your github repository.

Credits will be awarded based on:
    1. the expected data output, 
    2. code quality,
    3. project file/folder structure on github.

Expected S3 Object Keys:
project1/free-7-million-company-dataset-json.gzip
project1/free-7-million-company-dataset.parquet

Expected Github Content:
project1/s3.py

(This means you will need a different script to push the *s3.py* file to the s3 bucket)

Note: your script should have main method to make it easily executable from the command line.