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

## Structure

This project the following components:

1. create_tables.py creates the Sparkify star schema in Redshift.
2. etl.py defines the ETL pipeline, extracts data from S3, loads data into staging tables on Redshift, and then pushing the data in the final tables.
3. sql_queries.py defines the SQL queries of creation.
4. exploration.ipynb allows you to more interactively execute the ETL and run queries

## Instructions

In order to replicate this project, follow the below mentioned steps.

1. create a role in IAM , attach policies such as s3_read_acces, redshift_full_access.
2. create a user in IAM, keep a note of the access keys and the password.
3. create a redshift cluster, attach the role that we created in the redshift cluster.
4. Create a dwh.config file in the directory with the following structure


<pre>


[CLUSTER]
HOST=<your_host>
DB_NAME=<your_db_name>
DB_USER=<your_db_user>
DB_PASSWORD=<your_db_password>
DB_PORT=<your_db_port>


[IAM_ROLE]
ARN=<your_iam_role_arn>

[S3]
LOG_DATA='s3://udacity-dend/log_data'
LOG_JSONPATH='s3://udacity-dend/log_json_path.json'
SONG_DATA='s3://udacity-dend/song_data'

</pre>


## Schema for Song Play Analysis
Using the song and event datasets, we'll need to create a star schema optimized for queries on song play analysis. This includes the following tables.

### Fact Table

songplays - records in event data associated with song plays i.e. records with page NextSong

songplay_id, 
start_time, 
user_id, 
level, 
song_id, 
artist_id, 
session_id, 
location, 
user_agent


### Dimension Tables

users - users in the app


user_id, first_name, last_name, gender, level


songs - songs in music database


song_id, title, artist_id, year, duration


artists - artists in music database


artist_id, name, location, latitude, longitude


time - timestamps of records in songplays broken down into specific units


start_time, hour, day, week, month, year, weekday

## Create tables and insert data
To execute the ETL on an existing cluster from the command line, run the following:

<pre>
  
python3 create_tables.py
python3 etl.py
  
</pre>


## Query Example

Once you've created the database and run the ETL pipeline, you can test out queries, see example in the exploration.ipynb file





