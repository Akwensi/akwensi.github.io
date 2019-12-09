---
title: "Web Scraping with BeautifulSoup"
date: 2019-11-14
tags: [web scraping, scraping, batch processing, BeautifulSoup, requests, data mining]
header:
  image: "/webscraping.jpg"
excerpt: "Data engineering, Data Science, web scraping"
mathjax: "true"
---

# Web Scraping

This project sought to generate data on listings from a real estate website that can be used to study the type, location, pricing etc of the listings on the site. 

This can be achieved by parsing the data from the requests.get to **BeautifulSoup** to create a beautifulSoup *object*

Here is the [link](https://github.com/Akwensi/Web-scraping-_-project4) to the Jupyter notebook file created for this project with the codes.

NB: Because Scraping is an iterative process, there is the need to scrape each of the desired results singly before generalising for all of a particular element. 

## Task:

Write a python script that scrapes for info from meqasa and outputs a CSV file with the following structure:

property 
beds
showers
garages
area
description
price
currency
rent_period
url
address
time_posted
Property name
# of beds
# of showers
# of garages
Size of property
Description of property
Price of property
$, GHS, etc
month/week/year
Url to listing
Address of property
Datetime of listing



























