# Youtube-Videos-Analysis

*Goals* :
Data Ingestion — Build a mechanism to ingest data from different sources
ETL System — We are getting data in raw format, transforming this data into the proper format
Data lake — We will be getting data from multiple sources so we need centralized repo to store them
Scalability — As the size of our data increases, we need to make sure our system scales with it
Cloud — We can’t process vast amounts of data on our local computer so we need to use the cloud, in this case, we will use AWS
Reporting — Build a dashboard to get answers to the question we asked earlier

*Steps* :
* Create an IAM user in AWS and login using this user's credentials and not the root one.
* Open command line prompt and type "aws" to check if AWS CLI is installed on PC or not.
* Type "aws configure" and connect the aws by filling it's credentials.
* Goto AWS and click on 'S3' then create a new bucket.

![image](https://github.com/rishitamathur27/Youtube-Videos-Analysis/assets/38039850/7d3e3dea-8fd6-492d-a5a6-f7330e3cc3d0)


After this, upload the raw data in this bucket.

Open CLI:

->  aws s3 ls
->  Goto the folder where the data is downloaded:

    # To copy all JSON Reference data to same location:
  aws s3 cp . s3://youtube-raw-us-east-1-dev-de/youtube/raw_statistics_reference_data/ --recursive --exclude "*" --include "*.json"
   
    # To copy all data files to its own location, following Hive-style patterns:
  aws s3 cp CAvideos.csv s3://youtube-raw-us-east-1-dev-de/youtube/raw_statistics/region=ca/
  aws s3 cp DEvideos.csv s3://youtube-raw-us-east-1-dev-de/youtube/raw_statistics/region=de/
  aws s3 cp FRvideos.csv s3://youtube-raw-us-east-1-dev-de/youtube/raw_statistics/region=fr/
  aws s3 cp GBvideos.csv s3://youtube-raw-us-east-1-dev-de/youtube/raw_statistics/region=gb/
  aws s3 cp INvideos.csv s3://youtube-raw-us-east-1-dev-de/youtube/raw_statistics/region=in/
  aws s3 cp JPvideos.csv s3://youtube-raw-us-east-1-dev-de/youtube/raw_statistics/region=jp/
  aws s3 cp KRvideos.csv s3://youtube-raw-us-east-1-dev-de/youtube/raw_statistics/region=kr/
  aws s3 cp MXvideos.csv s3://youtube-raw-us-east-1-dev-de/youtube/raw_statistics/region=mx/
  aws s3 cp RUvideos.csv s3://youtube-raw-us-east-1-dev-de/youtube/raw_statistics/region=ru/
  aws s3 cp USvideos.csv s3://youtube-raw-us-east-1-dev-de/youtube/raw_statistics/region=us/
  
->  After uploading all the data to S3:
  






