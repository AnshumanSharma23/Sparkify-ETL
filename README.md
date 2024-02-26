# Data Warehouse Project

## Introduction
A music streaming startup named Sparkify has seen a significant increase in their user base and song database. To streamline their operations and utilize the scalability and flexibility of cloud computing, Sparkify has decided to migrate their data processes to the cloud. Currently, their data resides in Amazon S3, with JSON logs detailing user activity on the app and JSON metadata describing the songs available in the app.

As the data engineer responsible for this migration, our task is to build an Extract, Transform, Load (ETL) pipeline that extracts data from S3, stages it in Amazon Redshift, and transforms it into a set of dimensional tables. These tables will empower Sparkify's analytics team to derive valuable insights into user behavior and preferences, particularly focusing on the songs users are listening to.


## Project Description
In this project, you will leverage your knowledge of data warehousing concepts and Amazon Web Services (AWS) to implement an ETL pipeline for a database hosted on Amazon Redshift. The key steps involved in the project are as follows:

1. **Extract Data from S3**: Retrieve JSON data files from the specified S3 buckets containing user activity logs and song metadata.
2. **Stage Data in Redshift**: Load the raw data into staging tables in Amazon Redshift. Staging tables serve as an intermediate step before data transformation.
3. **Transform Data**: Execute SQL statements to transform the staged data into a set of dimensional tables optimized for analytics. This transformation involves tasks such as splitting JSON fields, joining tables, and aggregating data.
4. **Load Dimensional Tables**: Populate the dimensional tables with the transformed data, enabling efficient querying and analysis by Sparkify's analytics team.


