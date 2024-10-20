# Hadoop MapReduce Spark

Studies based in day 71-72, 73-74 and 79-80 of 100 Days System Design for DevOps and Cloud Engineers.

https://deoshankar.medium.com/100-days-system-design-for-devops-and-cloud-engineers-18af7a80bc6f

Days 71–80: High-Performance Computing (HPC) and Data Processing

Day 71–72: Set up a Hadoop cluster and perform data processing with Hadoop MapReduce.

Day 73–74: Implement a real-time data processing pipeline using Apache Flink.

Day 79–80: Optimize a Spark cluster for large-scale data processing.

## Project Overview

This study follow a [Setting up Hadoop with Docker and using MapReduce framework][3] tutorial to learn more about Hadoop ecosystem

### How to Use ```spark-basic-cluster```:

```
docker-compose up -d
docker cp ./spark_streaming.py spark-master:/spark_streaming.py
sudo apt-get install netcat
```

Mock streaming
```
nc -lk 9999
```

```
docker exec -it spark-master /spark/bin/spark-submit /spark_streaming.py
```

### How to Use ```flink-kafka-example```:

```
docker-compose up --build
```

Send Messages to Kafka:
```
docker exec -it flink-kafka-1 kafka-console-producer --broker-list localhost:9092 --topic flink-stream
```
These messages should be picked up by Flink, processed (converted to uppercase), and printed in the JobManager logs.

## Author
This project was implemented by [Lucas de Queiroz dos Reis][2]. It is based on the [100 Days System Design for DevOps and Cloud Engineers][1].

[1]: https://deoshankar.medium.com/100-days-system-design-for-devops-and-cloud-engineers-18af7a80bc6f "Medium - Deo Shankar 100 Days"
[2]: https://www.linkedin.com/in/lucas-de-queiroz/ "LinkedIn - Lucas de Queiroz"
[3]: https://medium.com/@guillermovc/setting-up-hadoop-with-docker-and-using-mapreduce-framework-c1cd125d4f7b "Medium - Guillermo Velazques"