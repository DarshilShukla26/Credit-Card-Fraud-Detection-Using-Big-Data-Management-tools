## README.txt

### Project Title:
Credit Card Fraud Detection Using Big Data Analytics

 Name: Darshil Shukla  
   Email: dshuk003@ucr.edu  
   Student ID: 862548182  

### Project Description:
This project leverages Big Data tools and machine learning techniques to detect fraudulent credit card transactions in real-time. The implementation uses Kafka for streaming, Spark for processing, MLlib for predictions, and Grafana for visualization.

### Running the Project:
1. Start Kafka Server and Zookeeper:
   - Before executing the code, ensure that the Kafka server and Zookeeper are running. The setup for Kafka is detailed in the provided `Kafka_Server_Setup.ipynb` notebook.

2. Configuration:
   - Attach the `Kafka.pem` file to configure the EC2 cluster for secure connections. Place the file in the project’s root directory and update the Kafka configurations accordingly.

3. Steps to Execute:
   - Start Zookeeper: Use the command `bin/zookeeper-server-start.sh config/zookeeper.properties`.
   - Start Kafka Server: Use the command `bin/kafka-server-start.sh config/server.properties`.
   - Run the processing pipeline by executing the provided scripts sequentially in the project repository. This step can also be run using the attached notebook on Google Colab for easier execution.

4. Producer Setup:
   - The `Producer.ipynb` notebook acts as a producer in the Kafka stream, passing messages to the consumer. Static data is used for this purpose, and the data file `data.csv` can be accessed via its Google Drive link.
   - Preprocessing steps include encoding and age calculation. The producer sends transactions to the Kafka topic `fraud-detection`.

5. Consumer Setup:
   - The `Spark_Consumer.ipynb` notebook acts as the consumer in the Kafka stream. It integrates Spark for processing and machine learning for fraud prediction.
   - Real-time predictions are made using a trained Random Forest model, and results are visualized using Plotly.
   - The training data `fraudTrain.csv` is used to train the model, while `data.csv` provides the input for predictions.

6. Spark Setup:
   - Ensure Spark is installed and configured correctly.
   - Set up the Spark environment using a SparkSession in Python.
   - Use PySpark for data preprocessing and machine learning tasks.

7. Machine Learning Model:
   - The machine learning model is defined in the `Spark_Consumer.ipynb` notebook. It loads training data available via a Google Drive link and generates the model using `RandomForestClassifier` from PySpark MLlib.
   - The next step involves using Spark and the Kafka consumer to make predictions and visualize results in real-time using plotly

### Prerequisites:
- Apache Kafka installed on the machine.
- Java installed and configured (Java 8 or later).
- Spark and its dependencies installed.
- `Kafka.pem` file placed in the root directory for secure Kafka cluster configuration.
- Install Python libraries: `kafka-python`, `pyspark` and `plotly`.

### Notes:
- For additional guidance, refer to the `Kafka_Server_Setup.ipynb` notebook.
- Ensure all required dependencies and configurations are correctly set up to avoid runtime issues.
- For any EC2 cluster details email at sgupt132@ucr.edu

For further queries, please contact the team members via the provided emails.
