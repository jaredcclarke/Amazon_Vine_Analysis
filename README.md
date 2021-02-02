# Amazon_Vine_Analysis
## Overview
### Purpose
The purpose of this analysis was to use PySpark to perform ETL on video game review data, connect to an AWS RDS Instance and load the transformed data into PostgreSQL. Then PySpark was used to determine if there is any bias toward favorable reviews from Vine members in the dataset.

### Resources/Tools
* Google Colaboratory
* PySpark 3.0.1
* PostgreSQL 11.9
* AWS RDS Instance
* Amazon Video Game Review Dataset

## Results/Summary
### Results
* Data was imported from Amazon dataset from S3 bucket
![](https://github.com/jaredcclarke/Amazon_Vine_Analysis/blob/main/Resources/df.png)

* Data was transformed to dataframe: 
 ![](https://github.com/jaredcclarke/Amazon_Vine_Analysis/blob/main/Resources/vine_df.png)

* Data loaded into PostgreSQL
![](https://github.com/jaredcclarke/Amazon_Vine_Analysis/blob/main/Resources/vine_table_query.png)

* This data was then filtered by `helpful_votes` that were ≥ 20, where `helpful_votes` /` total_votes` ≥ 50%, and then into two different groups: Paid (Vine Reviews) & Unpaid (Non-Vine Reviews)
* Paid dataframe

![](https://github.com/jaredcclarke/Amazon_Vine_Analysis/blob/main/Resources/vine_filtered_df.png)

* Summary of Paid reviews
![](https://github.com/jaredcclarke/Amazon_Vine_Analysis/blob/main/Resources/paid_stats.png)
* Total number of paid reviews: 94
* Total number of paid 5-star reviews: 48
* Percentage of paid reviews: 51.1% 

* Unpaid dataframe
![](https://github.com/jaredcclarke/Amazon_Vine_Analysis/blob/main/Resources/notvine_filtered_df.png)

* Summary of Unpaid reviews
![](https://github.com/jaredcclarke/Amazon_Vine_Analysis/blob/main/Resources/unpaid_stats.png)
* Total number of unpaid reviews: 40471
* Total number of unpaid 5-star reviews: 15663
* Percentage of paid reviews: 38.7% 

### Summary
The results of the analysis seem bias, because the paid 5-star reviews have a higher percentage than the unpaid 5-star reviews of heavily filtered data, but that is skewed since there so much fewer paid reviews than upaid reviews. 

To combat this, the analysis could posibly alter the `helpful_votes` filter to include more, or just look at the all the reviews for paid and unpaid, and for different star ratings.

 
