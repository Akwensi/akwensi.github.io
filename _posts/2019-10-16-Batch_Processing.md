---
title: "Batch Processing"
date: 2019-10-17
tags: [batch processing, transform, spark, pyspark, data mining, ngrams, bigrams trigrams]
header:
  image: "/data-engineering-banner.jpg"
excerpt: "Data engineering, Data Science, ngrams, trigrams"
mathjax: "true"
---

# Batch Processing

This project aimed at investigating the top keywords companies within various cities in the US require data scientists to have in their resume. 
All though Pandas could be used for this, we want to explore the power of Aparche Spark.

Here is the [link](https://github.com/Akwensi/Batch-Processing-for-Data-Mining_project2)? to the **Jupiter Notebook** file used in the project.  

*PySpark* and *Amazon Simple Storage Service(S3)* are the main technologies used in this project.
 
Your task is to:
  1. Create a Jupyter notebook that contains the following tasks:
Load the data scientist job market dataset and us stocks datasets from the s3 bucket ‘s3://blossom-data-engs’ onto your computer.
  2. Read the data with pyspark
  3. Read the alldata.csv from the data scientist datasets
  4. Join the 2 datasets.
  5. Write a function to generate n-grams (unigram & bigram) from a given text/description. 
  6. Write another function which uses the function from (5) to create 2 spark data frames which have 3 columns in the order of frequency: 
      a. {Ngram, City, Frequency}
      b. {Ngram, Industry, Frequency}

EXTRA POINTS: Use any visualization to compare a role between 2 cities
 ## **Commit this notebook into your github repo**
