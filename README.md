## Context:
This project aims to build a real-time data streaming pipeline, covering each phase from data ingestion to processing and finally storage. We'll utilize a powerful stack of tools and technologies, including Apache Airflow, Python, Apache Kafka, Apache Zookeeper, Apache Spark, and Cassandra—all neatly containerized using Docker.

## Project Objectives:
- Working with these data engineering tools in an individual local environment.
- Examining the workflow of streaming data processing, from extracting data via API to final storage.
- Integrating Airflow with Kafka to optimize orchestration
- 
## Acknowledgment:
Big thanks to Youtuber **CodewithYu** who instructed and guided me to create the complex pipeline successfully. Throughout the video, he tried to provide amazing awareness, offering valuable insights that significantly enhanced my understanding. His effort to deliver clear and engaging content has been a great resource for both beginners and those looking to refine their skills in data engineering.

## Challenges:
- Some details are unclear and outdated in the latest version
- Some essential steps are missing in the video
- the requirements also conflict with the specific version being used.

## Approaches:
- Verify the dependency requirements for the specific version of Airflow (in this case, the latest version) to prevent conflicts and ensure proper compatibility.
- Choose the right images for each containers
  
## Tools Used:
- Apache Airflow
- Apache Kafka
- Confluent Kafka
- Spark
- Docker Compose
- Cassandra

## Architecture
<p align="center">
<img src="https://github.com/user-attachments/assets/a38c34f0-9f4f-434d-ad36-8e7f3dacbe14" width=70% height=70%>
</p>

## Explanation
1. **API**:
    
    - **Purpose**: Serves as the data source, providing data to the pipeline. APIs can pull real-time data from external systems or applications.
    - **Use**: Feeds data to Apache Airflow for further processing.
2. **Apache Airflow**:
    
    - **Purpose**: Orchestrates workflows and pipelines. It schedules and monitors data ingestion and processing tasks.
    - **Use**: Manages the flow of data from the API to Kafka while storing metadata in PostgreSQL.
3. **PostgreSQL**:
    
    - **Purpose**: Stores metadata, logs, and task details for Apache Airflow.
    - **Use**: Supports the orchestration process by maintaining operational data.
4. **Kafka**:
    
    - **Purpose**: A distributed message broker used for real-time data streaming. It acts as the backbone of the streaming pipeline.
    - **Use**: Receives, buffers, and streams data to downstream consumers (e.g., Spark).
5. **Apache Zookeeper**:
    
    - **Purpose**: Manages and coordinates Kafka brokers and ensures fault tolerance.
    - **Use**: Acts as a central service to maintain Kafka's distributed architecture.
6. **Control Center**:
    
    - **Purpose**: Provides a graphical user interface to monitor and manage the Kafka cluster.
    - **Use**: Tracks Kafka metrics, health, and performance.
7. **Schema Registry**:
    
    - **Purpose**: Maintains and enforces schema compatibility for Kafka topics.
    - **Use**: Ensures producers and consumers adhere to the agreed data schema.
8. **Apache Spark**:
    
    - **Purpose**: Performs distributed and parallel data processing for high-speed data transformations and analysis.
    - **Use**: Processes streaming data from Kafka and prepares it for storage or further use.
9. **Cassandra**:
    
    - **Purpose**: A NoSQL database optimized for high write throughput and scalability.
    - **Use**: Stores processed data from Spark for real-time queries and analytics.
10. **Docker**:
    
    - **Purpose**: Containerizes the entire architecture, making it portable, scalable, and easier to deploy.
    - **Use**: Runs all the services in isolated, manageable containers.
