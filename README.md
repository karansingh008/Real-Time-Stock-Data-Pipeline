# Real-Time Stock Market Data Pipeline using Kafka and AWS

This project demonstrates the implementation of a real-time stock market data streaming, storage, and querying system using Apache Kafka and AWS cloud services. Developed as part of the Big Data Analytics course at VIT, it showcases end-to-end integration of distributed stream processing with cloud-native storage and serverless analytics.

## 💡 Overview

The pipeline collects live stock price data every 15 seconds using the Twelve Data API, streams it via Kafka (running on Amazon EC2), stores it in Amazon S3 as structured JSON, and enables query-based analysis using AWS Glue and Athena.

## 🔧 Technologies Used

- **Apache Kafka** (on AWS EC2): Distributed message queue
- **Python**: Core language for Producer & Consumer
- **Twelve Data API**: Live stock price feed
- **AWS S3**: Scalable cloud object storage
- **AWS Glue**: Schema inference and cataloging
- **Amazon Athena**: Serverless SQL querying
- **Google Colab**: Cloud-based environment for execution
- **Kafka-Python, boto3, s3fs**: Python libraries for integration

## ⚙️ Pipeline Components

### 🔹 Producer (Python + Kafka)
- Connects to Twelve Data API
- Fetches real-time stock prices every 15 seconds
- Streams data to Kafka topic `demo_test`
- Runs in Google Colab

### 🔹 Consumer (Kafka + AWS S3)
- Subscribes to the Kafka topic
- Writes each stock message as a uniquely named JSON file to an S3 bucket (`karan-stock-bucket`)
- Uses `boto3` and `s3fs` for AWS integration
- Executed in Google Colab

### 🔹 AWS Glue + Athena
- Glue Crawler automatically infers schema from S3 JSON files
- Athena enables real-time SQL queries over the dataset without provisioning servers

## 📁 Notebooks

- [Producer.ipynb](producer.ipynb)  
- [Consumer.ipynb](consumer.ipynb)

## 📊 Output

- 80+ JSON records successfully stored in S3
- Validated real-time producer-consumer flow
- Schema generated in Glue Data Catalog
- Queried records using Amazon Athena (live SQL analysis)

## 🧠 Concepts Demonstrated

- Real-time stream processing
- Decoupled microservice architecture
- Cloud-native storage & querying
- Secure credential management via environment variables
- Fault-tolerant message delivery with Kafka

## ✅ Prerequisites

- AWS account with access to EC2, S3, Glue, Athena
- Kafka running on EC2 (port 9092)
- Twelve Data API key
- Google Colab for execution (optional but used in this project)

## 📄 License

This project is for academic and demonstration purposes only.
