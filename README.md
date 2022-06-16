# Amazon_Vine_Analysis

## Overview

The goal of this exercise was to select a dataset of Amazon reviews (from the list <a href="https://s3.amazonaws.com/amazon-reviews-pds/tsv/index.txt">available here</a>) and use an ETL process to determine whether the reviews collected as part of the paid Amazon Vine program contained a disproportionate amount of 5-star reviews relative to reviews not part of the Vine program. I selected the "Watches" dataset available here: https://s3.amazonaws.com/amazon-reviews-pds/tsv/amazon_reviews_us_Watches_v1_00.tsv.gz

The ETL process involved using PySpark (in Google Colaboratory) to extract the dataset, transform the data, connect to an AWS RDS instance, and load the transformed data into pgAdmin. The transformed data was then exported out of pgAdmin as a .csv file and loaded into a Jupyter Notebook for further transformations and analysis using Python/Pandas. 


## Results

* How many Vine reviews and non-Vine reviews were there?
  * The total number of reviews written as part of the Vine program was 47. The total number of reviews NOT written as part of the Vine program was 8362.
* How many Vine reviews were 5 stars? How many non-Vine reviews were 5 stars?
  * The total number of 5-star reviews given in Vine reviews was 15. The total number of 5-star reviews given in non-Vine reviews was 4332.
* What percentage of Vine reviews were 5 stars? What percentage of non-Vine reviews were 5 stars?
  * The percentage of Vine reviews giving 5-star reviews was 31.914893617021278% . The percentage of NON-Vine reviews giving 5-star reviews was 51.80578808897393% .


Results: Using bulleted lists and images of DataFrames as support, address the following questions:

How many Vine reviews and non-Vine reviews were there?
How many Vine reviews were 5 stars? How many non-Vine reviews were 5 stars?
What percentage of Vine reviews were 5 stars? What percentage of non-Vine reviews were 5 stars?
Summary: In your summary, state if there is any positivity bias for reviews in the Vine program. Use the results of your analysis to support your statement. Then, provide one additional analysis that you could do with the dataset to support your statement.
