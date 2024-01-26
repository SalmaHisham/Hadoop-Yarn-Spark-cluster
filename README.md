# E-commerce Customer Behavior Analysis: Batch & Real-Time Workflows

## Overview
This project offers a dual approach to understanding e-commerce customer behavior through 
1. Batch data analysis ```/Main/For batch-data```
2. Real-time data processing. ```/Main/For Streaming-data```

The goal is to glean insights into purchasing patterns, product preferences, buying frequency, and the temporal impact on online shopping behavior to answer the following questions:

- Can we segment customers based on their demographic information (Age, Gender, City) and shopping behaviors (Total Spend, Number of Items Purchased, Membership Type)?
- Which customers are at risk of not making future purchases based on their Days Since Last Purchase and Satisfaction Level?
- Can we predict a customer’s Satisfaction Level based on their demographic and purchase history data?

**NOTE:** 
- You will find our visulizations and analysis here: ```/Analysis-report```
- Further information regarding Hadoop_Docker_cluster_setup is also provided in ```/Analysis-report```
## Dataset
Access the dataset at [E-commerce Customer Behavior Dataset](https://www.kaggle.com/datasets/uom190346a/e-commerce-customer-behavior-dataset).

## Tools and Technologies

- **Hadoop**:  To store and preprocess the large datasets of user logs and transaction data.
- **YARN**: To efficiently manage resources for complex analytics tasks
- **Apache Kafka**: To ingest real-time e-commerce transaction data.
- **Apache Spark Streaming** : For real-time data processing and to analyze customer behavior and predict future buying patterns.
- **PostgreSQL**: For storing  the the result of Data analysis and insights

---
## `1-` Batch Data Analysis:

### Objective

Employs a Hadoop Docker cluster and Apache Spark for batch processing. It extracts insights from the data to understand customer behavior to some questions and uses Logistic Regressin algorithm to analyze customer behavior and predict future buying patterns.

### Running the Application

1. Ensure Docker is installed.
2. Clone the repository.
3. Run Docker Compose:
 
    ```
    docker-compose up
    ```
4. Upload the dataset to HDFS:
    ```
    docker exec -it namenode hdfs dfs -put /path/to/E-commerceCustomerBehavior-Sheet1.csv /E-commerceCustomerBehavior-Sheet1.csv
    ```
5. Start analysis and preprocessing using PySpark:
    ```
    docker exec -it spark-master bash 
    ```
    ```
    spark-submit --master yarn /path/to/Analysis.py
    ```
    ```
    docker exec -it spark-master bash 
    ```
    ```
    spark-submit /path/to/predict.py
    ```
---

## `2-` Real-Time E-commerce Data Workflow:

### Objective
Introducing a real-time approach using Apache Kafka, Flume, and Spark Streaming to capture and analyze dynamic customer behavior, transactions, detecting anomalies in real-time and save it in **Hadoop HDFS** or **PostgreSQL**.


### Real-Time Workflow:

#### 1. Data Ingestion and Streaming
- Set up Kafka: Install and configure Apache Kafka to ingest real-time e-commerce transaction data. Define Kafka topics to categorize different types of transaction data.

#### 2. Stream Processing
- Use Apache Spark Streaming for real-time data processing, filtering, aggregating, and detecting anomalies in real-time.
- Implement Kafka Producer: Develop a Kafka producer to simulate or generate real-time e-commerce transactions and feed them into the Kafka topics.
- Run the correspoding stream Processing consumer to process the real-time data.


#### 3. Data Storage
- Store the processed data, including summaries and insights, in Hadoop HDFS or postgreSQL for further analysis and historical record-analysis.

#### 4. Generate Visual Reports
- Answer the previous questions in cool visualizations.


### Running the Real-Time Workflow

Same as before, except that the "preprocessing part" will be done by the **consumers**. To sum up:

![photo](https://github.com/nourhansowar/E-commerce-Customer-Behavior-Analysis/assets/48545560/1a4fcb0e-50c8-484b-a15f-3674cbce90a7)

1. **Start Kafka:** Ensure it's running with topics created.
2. **Run Kafka Producer:** Simulate or generate real-time transactions.
3. **Start Stream Processing:** Use Spark Streaming consumers to process real-time data.
4. **Store Processed Data:** Verify data is stored in Hadoop HDFS or PostgreSQL.
5. **Generate Visual Reports:** Utilize visualization tools for real-time insights.
---
By combining batch and real-time approaches, this project provides a comprehensive understanding of both historical and dynamic e-commerce customer behavior and that's it :D
