# Real-Time-Stock-Market-Data-Streaming-

Overview:

This project demonstrates a real-time data pipeline that streams stock market data using Apache Kafka, processes it, and stores it in AWS S3 for analysis. The pipeline is designed to handle large volumes of real-time data with fault tolerance and scalability, leveraging AWS services like EC2, S3, Glue, and Athena for data storage, processing, and querying.

Features:
Apache Kafka and ZooKeeper: Deployed on AWS EC2 instances to enable real-time streaming of stock market data.

Real-Time Data Processing: Streamed stock market data is processed with Python (using pandas) and sent to S3 in JSON format.

AWS Glue & Athena Integration: Automated crawling of S3 data using AWS Glue to create metadata tables and real-time querying of stock data with Amazon Athena.

Error Handling and Scalability: The pipeline includes optimizations like a 1-second delay to prevent Kafka overload and secure data transmission using AWS IAM roles.

Project Architecture:
![Architecture](https://github.com/user-attachments/assets/f076de14-f47e-4504-8031-7fd82f290395)



Kafka Setup on EC2:

Launched an AWS EC2 instance and installed Apache Kafka and ZooKeeper for distributed messaging.
Configured SSH access to EC2 and installed Java to support Kafka dependencies.

Kafka Producer & Consumer:
Built a Kafka producer to ingest real-time stock market data.
Data is processed using pandas and sent via the Kafka consumer to an AWS S3 bucket in JSON format.

Data Storage & Querying:
AWS S3 is used for storing the streamed data in JSON format.
AWS Glue crawls the S3 bucket to generate a data catalog, enabling easy access for querying via Amazon Athena.

Optimization & Security:
A 1-second delay was introduced in the Kafka producer to prevent overload during high data volume periods.
Ensured secure data flow and access management using IAM roles for resource authorization.


Installation & Setup

AWS EC2 Instance:
Launch an EC2 instance with SSH access and install Apache Kafka and ZooKeeper.

Install Java dependencies for Kafka to work properly.


Kafka Producer & Consumer:
Set up a Kafka producer to fetch real-time stock data.

Set up a Kafka consumer that processes the data and pushes it to an S3 bucket in JSON format.


AWS Services:
Use AWS Glue to crawl the S3 bucket, generating metadata for real-time querying of stock data through Athena.


Usage


Start Kafka:


Launch ZooKeeper: zookeeper-server-start.sh config/zookeeper.properties

Start Kafka: kafka-server-start.sh config/server.properties


Run Producer:
Execute the Kafka producer script to start streaming stock market data.


Run Consumer:
Execute the Kafka consumer to process and store data in the S3 bucket.


Query Data:
Use Amazon Athena to query stock data from the S3 bucket in real time.

Technologies Used

Apache Kafka: Distributed data streaming
ZooKeeper: Service coordination for Kafka
AWS EC2: Compute instance for Kafka
AWS S3: Data storage
AWS Glue: Data catalog and ETL
Amazon Athena: Querying data stored in S3
Python: Data processing (pandas)
