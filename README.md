# Amazon_Vine_Analysis

## Overview

The goal of this exercise was to select a dataset of Amazon reviews (from the list <a href="https://s3.amazonaws.com/amazon-reviews-pds/tsv/index.txt">available here</a>) and use an ETL process to determine whether the reviews collected as part of the paid Amazon Vine program contained a disproportionate amount of 5-star reviews relative to reviews not part of the Vine program. I selected the "Watches" dataset available here: https://s3.amazonaws.com/amazon-reviews-pds/tsv/amazon_reviews_us_Watches_v1_00.tsv.gz

The ETL process involved using PySpark (in Google Colaboratory) to extract the dataset, transform the data, connect to an AWS RDS instance, and load the transformed data into pgAdmin. The transformed data was then exported out of pgAdmin as a .csv file and loaded into a Jupyter Notebook for further transformations and analysis using Python/Pandas. 


## Results

The following is an image of the top of the complete vine_table data exported from pgAdmin:

![16_vine_table_pgadmin](https://user-images.githubusercontent.com/100863488/174141364-9e3d7fce-8386-4263-bc25-5be0e06a6899.png)


The following is an image of the two dataframes created with Python/Pandas to learn more about Vine and non-Vine reviews:

![16_vine_tablesjup](https://user-images.githubusercontent.com/100863488/174141385-8e94a86a-cadc-4056-8db0-e459cc89210b.png)



As part of the ETL process, the table of reviews was filtered to remove any reviews with fewer than 20 votes in the "total votes" column, as well as any reviews where the votes marked "helpful" did not comprise at least 50% of the total votes for a review. After this filtering of the dataset:

* How many Vine reviews and non-Vine reviews were there?
  * The total number of reviews written as part of the Vine program was 47. The total number of reviews NOT written as part of the Vine program was 8362.
* How many Vine reviews were 5 stars? How many non-Vine reviews were 5 stars?
  * The total number of 5-star reviews given in Vine reviews was 15. The total number of 5-star reviews given in non-Vine reviews was 4332.
* What percentage of Vine reviews were 5 stars? What percentage of non-Vine reviews were 5 stars?
  * The percentage of Vine reviews giving 5-star reviews was 31.915%. The percentage of NON-Vine reviews giving 5-star reviews was 51.806%.


## Summary

From these results it does not appear that there is any positivity bias for 5-star reviews in the Vine program, since the percentage of 5-star reviews among all Vine (paid) reviews in this dataset was 31.9%, and the percentage of 5-star reviews among non-paid reviews was 51.8%.

An additional analysis that could be performed with this dataset could involve the "Verified Purchase" column of information. It is my understanding that "Verified Purchase" refers to reviews left by customers who purchased the item directly through Amazon. Reviews without a "verified purchase" therefore do not have any confirmation that the individual bought or owns the product being reviewed, and these could be reviews created by bots to increase the rating artificially, reviews left by consumers who purchased the item in other locations, etc. It would be helpful to have data regarding the relative star ratings between users who had a "verified purchase" of the item versus users who did not.

If there is a large discrepancy between the non-Vine (unpaid) "Verified Purchase" reviews and the non-Vine reviews not associated with a Verified Purchase, that may cause us to interpret our Vine/non-Vine results differently. If the majority of non-Vine 5-star ratings are from users without a Verified Purchase, but the majority of Vine 5-star ratings are from users with a Verified Purchase, we may have reason to reconsider our conclusion regarding Vine positivity bias.


