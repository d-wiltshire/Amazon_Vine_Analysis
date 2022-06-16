# Amazon_Vine_Analysis

## Overview

The goal of this exercise was to select a dataset of Amazon reviews (from the list <a href="https://s3.amazonaws.com/amazon-reviews-pds/tsv/index.txt">available here</a>) and use an ETL process to determine whether the reviews collected as part of the paid Amazon Vine program contained a disproportionate amount of 5-star reviews relative to reviews not part of the Vine program. I selected the "Watches" dataset available here: https://s3.amazonaws.com/amazon-reviews-pds/tsv/amazon_reviews_us_Watches_v1_00.tsv.gz

The ETL process involved using PySpark (in Google Colaboratory) to extract the dataset, transform the data, connect to an AWS RDS instance, and load the transformed data into pgAdmin. The transformed data was then exported out of pgAdmin as a .csv file and loaded into a Jupyter Notebook for further transformations and analysis using Python/Pandas. 


## Results

The following is an image of the top of the complete vine_table data exported from pgAdmin:

![16_vine_table_pgadmin](https://user-images.githubusercontent.com/100863488/174141364-9e3d7fce-8386-4263-bc25-5be0e06a6899.png)


The following is an image of the two dataframes created with Python/Pandas to learn more about Vine and non-Vine reviews:

![16_vine_tablesjup](https://user-images.githubusercontent.com/100863488/174141385-8e94a86a-cadc-4056-8db0-e459cc89210b.png)



* How many Vine reviews and non-Vine reviews were there?
  * The total number of reviews written as part of the Vine program was 47. The total number of reviews NOT written as part of the Vine program was 8362.
* How many Vine reviews were 5 stars? How many non-Vine reviews were 5 stars?
  * The total number of 5-star reviews given in Vine reviews was 15. The total number of 5-star reviews given in non-Vine reviews was 4332.
* What percentage of Vine reviews were 5 stars? What percentage of non-Vine reviews were 5 stars?
  * The percentage of Vine reviews giving 5-star reviews was 31.914893617021278% . The percentage of NON-Vine reviews giving 5-star reviews was 51.80578808897393% .


## Summary

From these results it does not appear that there is any positivity bias for 5-star reviews in the Vine program, since the percentage of 5-star reviews among all Vine (paid) reviews in this dataset was 31.9%, and the percentage of 5-star reviews among non-paid reviews was 51.8%.

Then, provide one additional analysis that you could do with the dataset to support your statement.
