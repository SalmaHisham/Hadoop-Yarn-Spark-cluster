# Batch E-commerce Customer Behavior Analysis

## Tools and Technologies
- HADOOP
- YARN
- Apache Spark


## Tasks

- Hadoop Role: Store and preprocess the large datasets of user logs and transaction data.
- Spark Role: Use machine learning algorithms to analyze customer behavior and predict future buying patterns.
- YARN Role: Efficiently manage resources for complex analytics tasks. 


## Running the Application
To run the application, we have set up a Hadoop Docker cluster. The Hadoop cluster will be responsible for storing and preprocessing the large datasets of user logs and transaction data. Additionally, we will utilize Apache Spark, a powerful distributed computing framework, to perform machine learning algorithms for analyzing customer behavior and predicting future buying patterns.

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

After uploading the dataset, you can start the analysis and preprocessing using PySpark. The analysis code is available in the project repository. You can run it using the following command:
```
docker exec -it spark-master spark-submit /path/to/Analysis.py
```
```
docker exec -it spark-master spark-submit /path/to/predict.py
```