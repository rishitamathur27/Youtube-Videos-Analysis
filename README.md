# Youtube-Videos-Analysis

*Goals* :
1. Data Ingestion — Build a mechanism to ingest data from different sources.
2. ETL System — We are getting data in raw format, transforming this data into the proper format.
3. Data lake — We will be getting data from multiple sources so we need centralized repo to store them.
4. Scalability — As the size of our data increases, we need to make sure our system scales with it.
5. Cloud — We can’t process vast amounts of data on our local computer so we need to use the cloud, in this case, we will use AWS.
6. Reporting — Build a dashboard to get answers to the question we asked earlier.

*Steps* :
* Create an IAM user in AWS and login using this user's credentials and not the root one.
* Open command line prompt and type "aws" to check if AWS CLI is installed on PC or not.
* Type "aws configure" and connect the aws by filling it's credentials.
* Goto AWS and click on 'S3' then create a new bucket.

![image](https://github.com/rishitamathur27/Youtube-Videos-Analysis/assets/38039850/7d3e3dea-8fd6-492d-a5a6-f7330e3cc3d0)


After this, upload the raw data in this bucket.

Open CLI:

*  aws s3 ls
*  Goto the folder where the data is downloaded:

  -----To copy all JSON Reference data to same location:-----
  
  aws s3 cp . s3://youtube-raw-us-east-1-dev-de/youtube/raw_statistics_reference_data/ --recursive --exclude "*" --include "*.json"
   
  -----To copy all data files to its own location, following Hive-style patterns:-----
  * aws s3 cp CAvideos.csv s3://youtube-raw-us-east-1-dev-de/youtube/raw_statistics/region=ca/
  * aws s3 cp DEvideos.csv s3://youtube-raw-us-east-1-dev-de/youtube/raw_statistics/region=de/
  * aws s3 cp FRvideos.csv s3://youtube-raw-us-east-1-dev-de/youtube/raw_statistics/region=fr/
  * aws s3 cp GBvideos.csv s3://youtube-raw-us-east-1-dev-de/youtube/raw_statistics/region=gb/
  * aws s3 cp INvideos.csv s3://youtube-raw-us-east-1-dev-de/youtube/raw_statistics/region=in/
  * aws s3 cp JPvideos.csv s3://youtube-raw-us-east-1-dev-de/youtube/raw_statistics/region=jp/
  * aws s3 cp KRvideos.csv s3://youtube-raw-us-east-1-dev-de/youtube/raw_statistics/region=kr/
  * aws s3 cp MXvideos.csv s3://youtube-raw-us-east-1-dev-de/youtube/raw_statistics/region=mx/
  * aws s3 cp RUvideos.csv s3://youtube-raw-us-east-1-dev-de/youtube/raw_statistics/region=ru/
  * aws s3 cp USvideos.csv s3://youtube-raw-us-east-1-dev-de/youtube/raw_statistics/region=us/
  
->  After uploading all the data to S3:

* Click on AWS Glue.
* Goto: Data Catalog--> Crawlers
![image](https://github.com/rishitamathur27/Youtube-Videos-Analysis/assets/38039850/89d5158d-7f4a-4aaf-818d-77d43087418e)
![image](https://github.com/rishitamathur27/Youtube-Videos-Analysis/assets/38039850/58e39c6c-f3b1-4f3b-aa34-d1da741f7ab7)

* Create an IAM role.
  When a service wants to access another service in AWS (glue wants to access data from S3), it doesn't have direct permission. Create a   Role would give this permission.
  
  Create Role --> 
  ![image](https://github.com/rishitamathur27/Youtube-Videos-Analysis/assets/38039850/70efc93e-f391-4807-b4ac-76d4e8e4a234)

  ![image](https://github.com/rishitamathur27/Youtube-Videos-Analysis/assets/38039850/3d0a1d52-0fbf-4a9d-aa1b-28f986e55fef)
  
  ![image](https://github.com/rishitamathur27/Youtube-Videos-Analysis/assets/38039850/e24b3b73-d273-4563-8327-f906652c29ba)

* Click on Attach policies:
  ![image](https://github.com/rishitamathur27/Youtube-Videos-Analysis/assets/38039850/da5ce8ec-4400-405e-af61-aa441af4e78b)
  
  ![image](https://github.com/rishitamathur27/Youtube-Videos-Analysis/assets/38039850/372bea7c-5025-47b6-8e50-c804166885e5)

* Goto AWS Glue and select the role:
  ![image](https://github.com/rishitamathur27/Youtube-Videos-Analysis/assets/38039850/796fc4e9-874c-4be9-8be8-57c72810ac9c)
  
* Add database
  ![image](https://github.com/rishitamathur27/Youtube-Videos-Analysis/assets/38039850/3b709e6e-fe2d-4d60-a631-e65d959c11c7)

  Click on 'Run'
  
  
  


  






