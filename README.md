# Spotify-Data-Pipeline

### Introduction
In this project, we build an ETL pipeline using the spotify API on AWS. The pipeline retrieves data from the Spotify API, transform it to a desired format and load it to AWS Storage.

### Architecture
![Architecture Diagram](https://github.com/KartikAnand17/Spotify-Data-Pipeline/blob/main/Architecture_spotify.png)

### About Dataset/API
This API consists information about artist, albums and songs from the spotify application - [Spotify API](https://developer.spotify.com/documentation/web-api)

### Services Used
1. **S3 (Simple Storage Service):** Amazon S3 is a highly scalable object storage service that can store and retrieve any amount of data from anywhere on the web. It is commonly used to store and distribute large media files, data backups, and static website files.

2. **AWS Lambda:** AWS lambda is a serverless computing service that lets you run your code without managing servers. You can use Lambda to run code in response to events like changes in S3, DynamoDB, or other AWS services.

3. **Cloud Watch:** Amazon cloudwatch is a monitoring service for AWS resources and the applications you run on them. You can use CloudWatch to collect and track metrics, collect and monitor log files, and set alarms.

4. **Glue Crawler:** AWS Glue Crawler is a fully managed service that automatically crawls you data sources, identifies data formats and infers schema to create an AWS Glue Catalog.

5. **Data Catalog :** AWS Glue Data Catalog is a fully managed metadata repository tbat makes it easy to discover and manage data in AWS. You can use the Glue Catalog with other services, such as Athena.

6. **Amazon Athena :** Amazon Athena is an interactive query service that makes it easy to analyze data in Amazon S3 using standard SQL. You can use Athena to analyze data in your Glue Data Catalog or in other S3 buckets.

### Install Packages
```
pip install pandas
pip install numpy 
pip install spotipy
```

### Project Execution Flow
Extract Data from API -> Lambda Trigger (every 1 hour) -> Run extract Code -> Store Raw Data -> Trigger Transform Function -> Transform Data and Load it in S3 -> Query using Athena
