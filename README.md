# Amazon Vine Analysis
## Overview
As the first data expert at BigMarket, a startup company that helps businesses optimize their marketing efforts, I am required to assist one of BigMarket’s clients SellBy to run some hefty analytics. SellBy is about to release a large catalog of products on a leading retail website. They want to know how the reviews of their products compare to the reviews of similar products sold by their competitors. Aside from this, they also want to enroll in a program that gives out free products to select reviewers, but they would want to know if it is worth the cost.
I will be analyzing Amazon reviews written by members of the paid Amazon Vine program. The Amazon Vine program is a service that allows manufacturers and publishers to receive reviews for their products. SellBy has paid a small fee to Amazon and provided products to Amazon Vine members, who are required to publish a review.

In this project, 50 datasets of product categories are available to chose from. I chose to analyze reviews in the Camera category. I used PySpark to perform the ETL process to extract the dataset, transform the data, connect to an AWS RDS instance, and load the transformed data into pgAdmin. Next, using PySpark, I determined if there is any bias toward favorable reviews from Vine members in the dataset.

## Results 
The raw data had 1801974 rows. I created a Vine data frame which had columns review_id, star_rating, helpful_votes, total_votes, vine, and verified_purchase". I filtered this dataframe based on reviews that had more than 20 total votes, and at the same time have the number of helpful votes divided by the number of total votes being equal to or greater than 50%. This reduced the number of rows to 51129. The resulting table is shown below:

![image1](https://github.com/GerlechJen/Amazon_Vine_Analysis/blob/main/Images/helpful_votes.png)

The data frame above was further filtered into two to obtain a Vine data frame where a review was written as part of the Vine program and a non Vine data frame where the review was not part of the Vine program. The vine data frame is shown below:


![image2](https://github.com/GerlechJen/Amazon_Vine_Analysis/blob/main/Images/vine%20data%20frame%20.png)

Below is the non Vine dataframe 

The total number of reviews for the Vine and non-Vine programs were found next. Both counts are shown below:





* After the analysis, it was discovered that there were 607 Vine reviews and 50,522 non-Vine reviews as seen from the image above.
* Out of the 607 Vine reviews, 257 were 5 stars and 25,220 out of the 50,522 non-Vine reviews were 5 stars. The results is shown in the image below:


* 42.3% of Vine reviews were 5 stars and 49.9% of non-Vine reviews were 5 stars


## Summary 
From the results given, there isn't any positivity bias for reviews in the Vine program. This is because the percentage of 5-star reviews for the Vine program was less compared to the percentage of 5-star reviews for the non-Vine reviews. 
This conclusion can be further examined by finding the percentage of all stars(1,2,3,and 4 stars) for paid and unpaid reviews. Aside from that this same analysis can be performed on a few more different categories of products for a more thorough analysis.



