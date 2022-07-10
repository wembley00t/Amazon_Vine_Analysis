# Amazon_Vine_Analysis

# Purpose

The purpose of this project is to analyze Amazon reviews written by members of the paid Amazon Vine Program.  The Amazon Vine program
is a service that allows manufacturers and publishers to receive reviews for their products.  Companies pay a small fee to Amazon and provide
products to Amazon Vine members, who are required to publish a review.

The beauty dataset was selcted for this project.  PySpark was used to perform the ETL process to extract the dataset, transform the data,
connect to an AWS RDS instance and load the transformed data into pgAdmin.  PySpark was used to determine if there is any bias toward favorable
reviews from Vine members in the dataset.

# Results

To obtain the results, PySpark was used to read in the url for the beauty dataset.  The data frame was set up by converting it to a 
csv.  The data frame for the Vine Program included the data elements of review id, star rating, helpful votes, total votes, vine as Y/N and 
verified purchase.  The data frame was further refined to filter for items with total votes greater than or equal to 20.  Next a data frame
was created by continuing to filter the data.  This data frame filtered for helpful votes as a percent of total votes being greater than or 
equal to 50%.  Finally 2 data frames were created based on filtering for the Vine program.  Reviews that were included in the Vine program are
reflected in the paid reviews data frame.  Reviews not part of the Vine program were included in the unpaid reviews data frame.

An image of the final two data frames for paid and unpaid reviews is shown below.  

![paid reviews](https://user-images.githubusercontent.com/100876517/178141239-a5f6a06a-f315-427d-afae-02b33afbf08e.png)
![unpaid reviews](https://user-images.githubusercontent.com/100876517/178141242-de783fbe-8e9e-44f5-b3fb-de76fb0a0a3c.png)




## Dataset Findings

* As detailed below, there are a total of 74,760 reviews in the dataset.  Paid reviews totaled 647 while unpaid reviews totaled 74,113.

![1st question](https://user-images.githubusercontent.com/100876517/178127926-5e5278e0-44ab-421c-9a1d-5ec7bdc4e9ed.png)

![code question 1](https://user-images.githubusercontent.com/100876517/178128211-92cec58d-9f7d-4c17-9a2d-c104f43c020e.png)

* The number of 5-star reviews for the paid reviews totaled 229 compared to the total 5-star reviews for the unpaid reviews of 43,217.

![2nd question](https://user-images.githubusercontent.com/100876517/178127928-1e3da7b5-1401-4b4a-a1ba-a226ffe184f2.png)

![code question 2](https://user-images.githubusercontent.com/100876517/178128210-6b6adb71-1358-496e-8b34-b6518e667f7f.png)

* The paid reviews reflect that 35% of their reviews are 5-star reviews compared to 58% for the unpaid reviews.

![3rd question](https://user-images.githubusercontent.com/100876517/178127929-d8db099a-e675-4571-bbfe-6b56289e5f12.png)

![code question3](https://user-images.githubusercontent.com/100876517/178128209-41c3d643-df91-404e-9fde-247342204f9c.png)

# Summary

The reviews in the Vine program do not indicate positivity bias.  Within the Vine paid reviews data, only 35% of the reviews are 5-star.  This is
compared to 58% for the unpaid reviews.  


