# Real-Time E-commerce Data Workflow

## Tools and Technologies
- HADOOP
- YARN
- Apache Spark Streaming 
- Apache Kafka
- Flume
- PostgreSQL

## Tasks
1. Data Ingestion and Streaming

- Set up Kafka: Install and configure Apache Kafka to ingest real-time e-commerce transaction data. Define Kafka topics to categorize different types of transaction data.

2. Stream Processing

- Use Apache Spark Streaming for real-time data processing, filtering, aggregating, and detecting anomalies in real-time.
- Implement Kafka Producer: Develop a Kafka producer to simulate or generate real-time e-commerce transactions and feed them into the Kafka topics.


3. Data Storage

Hadoop HDFS: Store the processed data, including summaries and insights, in Hadoop HDFS or postgreSQL for further analysis and historical record-analysis.

4. Generate Visual Reports

Answer the following Questions:
- Can we segment customers based on their demographic information (Age, Gender, City) and shopping behaviors (Total Spend, Number of Items Purchased, Membership Type)?
- Which customers are at risk of not making future purchases based on their Days Since Last Purchase and Satisfaction Level?
- Can we predict a customer’s Satisfaction Level based on their demographic and purchase history data?

## Real-time data workflow:

1. **Start Kafka**: Ensure that Apache Kafka is running and Kafka topics are created.
2. **Run Kafka Producer**: Execute the Kafka producer script to simulate or generate real-time e-commerce transactions.
3. **Start Stream Processing consumer**: Run the Apache Spark Streaming framework to process the real-time data.
4. **Store Processed Data consumer**: Verify that the processed data is stored in Hadoop HDFS.
5. **Generate Visual Reports consumer**: Utilize the visualization tool to generate visual reports based on real-time data.


## Running the Application
Please follow the steps below to run the application:

- Ensure that you have Docker installed on your machine.
- Clone the project repository to your local machine.
- Navigate to the project directory.
- Run the Docker Compose file using the following command:
```
docker-compose up
```
This will start the Hadoop cluster and make it available for processing the dataset.
Once the cluster is up and running, you can upload and store the dataset in the Hadoop Distributed File System (HDFS). You can use the following command to upload the dataset:
```
docker exec -it namenode hdfs dfs -put /path/to/E-commerceCustomerBehavior-Sheet1.csv /E-commerceCustomerBehavior-Sheet1.csv
```

After uploading the dataset, you can start the analysis and preprocessing using Spark stream. 

The analysis code is available in the project repository under the `Main foler`. You can run it using the following command:
```
docker exec -it spark-master spark-submit /kafka_producer_ecommerce.py
```
```
docker exec -it spark-master spark-submit /kafaka_consumer_ecommerce_to_console.py
```


