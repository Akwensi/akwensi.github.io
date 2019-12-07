---
title: "Data Engineering Project: Basic ETL pipeline"
date: 2019-10-12
tags: [data engineering, basic etl, loading datasets, s3, s3 bucket] 
header:
    image: "/images/data-engineering-1.jpeg"
    excerpt: "Data Science, loading datasets to s3, s3, s3 bucket"
---
# Basic Extract Transform Load (ETL) 
This project was to basically load data from an existing s3-bucket on *AWS*, transform the data by doing some **aggregations** and then loading it back to the s3-bucket.
Here is a [link](https://github.com/Akwensi/project1) to the jupyter notebookfile used for this project

You can download folow along
1. confirm the file exist in the s3 bucket
2. use the boto3 library to download the data locally
etc. etc

Python code block:
    ```python
        import boto3
        import Pandas as pd