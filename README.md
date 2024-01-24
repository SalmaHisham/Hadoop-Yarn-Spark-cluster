# E-commerce Customer Behavior Analysis: Batch & Real-Time Workflows

## Overview

This project offers a dual approach to understanding e-commerce customer behavior through 
1. Batch data analysis
2. Real-time data processing. 

Utilizing historical and dynamic datasets, the goal is to glean insights into purchasing patterns, product preferences, buying frequency, and the temporal impact on online shopping behavior.

## Dataset
Access the dataset at [E-commerce Customer Behavior Dataset](https://www.kaggle.com/datasets/uom190346a/e-commerce-customer-behavior-dataset).

#### Tools and Technologies
- **Stream Processing:** Apache Kafka and Apache Flink
- **Database:** Any suitable database (e.g., PostgreSQL, MongoDB)

## Batch Data Analysis:

### Objective
Employs a Hadoop Docker cluster and Apache Spark for batch processing. It extracts insights from historical data to understand customer behavior to some questions.


#### Running the Application
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
    docker exec -it spark-master spark-submit /path/to/Analysis.py
    ```
    ```
    docker exec -it spark-master spark-submit /path/to/predict.py
    ```


## Real-Time E-commerce Data Workflow:

### Objective
Introducing a real-time approach using Apache Kafka and Flume and Spark Streaming to capture and analyze dynamic customer behavior and transactions.



#### Real-Time Workflow:

##### 1. Data Ingestion and Streaming
- **Set up Kafka:** Install and configure Apache Kafka for real-time e-commerce transaction data.

##### 2. Stream Processing
- **Choose Processing Framework:** Select either Apache Flink or Apache Spark Streaming.
- **Implement Kafka Producer:** Simulate real-time transactions and feed them into Kafka topics.
- **Processing Logic:** Use the chosen framework to filter, aggregate, and enrich real-time data.

##### 3. Data Storage
- **Hadoop HDFS:** Store processed data, summaries, and insights for historical analysis.

##### 4. Generate Visual Reports
- **Visualization Tool:** Utilize tools like Matplotlib or Tableau to create visual reports.
- **Database Storage:** Store visualized data and insights in a suitable database.

#### Implementation
- **Integration:** Merge real-time workflow with the existing project.
- **Continuous Processing:** Ensure continuous real-time processing and implement monitoring mechanisms.
- **Documentation:** Update the README with steps for running the real-time workflow.

#### Running the Real-Time Workflow
1. **Start Kafka:** Ensure it's running with topics created.
2. **Run Kafka Producer:** Simulate or generate real-time transactions.
3. **Start Stream Processing:** Use Flink or Spark Streaming to process real-time data.
4. **Store Processed Data:** Verify data is stored in Hadoop HDFS.
5. **Generate Visual Reports:** Utilize visualization tools for real-time insights.

By combining batch and real-time approaches, this project provides a comprehensive understanding of both historical and dynamic e-commerce customer behavior.