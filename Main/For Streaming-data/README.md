# Real-Time E-commerce Data Workflow

## Tools and Technologies
- HADOOP
- YARN
- Apache Spark Streaming 
- Apache Kafka
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


## Running the Real-Time Workflow:

### Local mode:

  * Launch ZooKeeper: Start ZooKeeper by running the following command:
```    
zookeeper-server-start.sh config/zookeeper.properties
```
  * Run kafka_producer.py: Execute the script to generate real-time data. This will simulate the generation of e-commerce transactions.
```
python kafka_producer.py
```
  * Run kafka_consumer_detect_anomalies.py: Start the Kafka consumer script that consumes the generated data and detects anomalies in real-time.
```
python kafka_consumer_detect_anomalies.py
```
  * Push the results to PostgreSQL: Store the processed data, including any detected anomalies, in PostgreSQL for further analysis and record-keeping.

### Cluster mode:
![photo](https://github.com/nourhansowar/E-commerce-Customer-Behavior-Analysis/assets/48545560/4cf462e6-d3cb-4be8-a5d7-12351d2824c8)


  * Launch the entire Docker Compose cluster configuration by executing the following command:
```
docker-compose -f all-docker-compose.yaml up
```
  * Run Kafka Producer in Kafka Broker container: Simulate or generate real-time transactions by running the Kafka producer script within the Kafka Broker container.

  * Run the consumer in Spark container: Execute the Spark consumer script within the Spark container to process the real-time data and perform any necessary analysis or anomaly detection.


