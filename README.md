# Analyzing Outdoor Products Reviews on Amazon

## Objective 
The ojective of this assigment is to analyze Amazon reviews written by members of the paid Amazon Vine program. In this project, we will have access to approximately 50 datasets. Each one contains reviews of a specific product, from clothing apparel to wireless products. We selected the outdoor products review to use in our analysis. 

Since the data is large the workflow we used is  Big Data, PySpark ,and AWS. First we create RDS database, S3 storage for large .csv file. Then we connect the RDS server to pgAdmin. The raw data have to be cleaned up using ETL process, then we performed analysis in PySpark to determine whether the Vine reviews were biased.

## ETL Process 
Product table 
Load Amazon Data into Spark DataFrame and generate product table which has : product_id, and product_title. The total data in product table are 391729 after cleaning duplicates.

________________________________________________________________________________________________________________________________________________________________________
Customer table 
Customer table include customer id, and customer count has total data of 1516428 data after cleaning and combine and the summary table shown below :


  The Customer table  : 
  ![alt text][Image1]
  
  [Image1]: https://github.com/ttan0408/Amazon_Vine_Analysis/blob/main/customer%20table.PNG "The Customer table"

________________________________________________________________________________________________________________________________________________________________________
Review ID table 
In the review id data table , we have to conver the data colume into data format because it is in string format in the raw data set.

Review ID table  : 
![alt text][Image2]
  
[Image2]: https://github.com/ttan0408/Amazon_Vine_Analysis/blob/main/customer%20table.PNG "Review ID table "

_________________________________________________________________________________________________________________________________________________________________________
Vine Review table
Final table we have to convert into is the vine review table and it shown below:

## Analysis and Conclusion :
The goal is to determine if there is any bias toward favorable reviews from Vine members in outdoor produc dataset. The focus data table we used is vine review table. First we have to separate the vine table into two categories : paid and unpaid . Before to separate them into categories we have to filter the vine review table so that we only have helpful review data which has the total votes > 20 and the ratio between helpful vote to total votes greater than 50%.

From the analysis there are total of 43574 helpful vine review and that includes 21372 of 5 star review. The average rating between vine paid and unpaid is 4.3 and 3.9 respectively. This indicate the review data set is unbiased. Also 98% five star review are from unpaid where the customer are the independent opinions of the Vine Voices

The ipynb file link is located below :
