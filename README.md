# Spring Boot with Kafka Producer Example
This Project covers how to use Spring Boot with Spring Kafka to Publish JSON/String message to a Kafka topic

- `As windows was not working for me as expected, I have installed linux- subsystem for linux and isntalled java, kafka, maven on it`
## use full commands in linux
- `Command1: apt-get update && apt-get upgrade   --> this is update the all the packages` 
- `Command2: apt install default-jre  --> this will install default-java`


## Start Zookeeper
- `bin/zookeeper-server-start.sh config/zookeeper.properties`

## Start Kafka Server
- `bin/kafka-server-start.sh config/server.properties`

## List out all the topics in kafka
- `bin/kafka-topics.sh --list --zookeeper localhost:2181`

## Delete all the message in the kafka topic, you need to decrease the retention period to one second
- `kafka-topics.sh --zookeeper localhost:2181 --alter --topic Kafka_Example --config retention.ms=1000`
 
## Create Kafka Topic
- `bin/kafka-topics.sh --create --zookeeper localhost:2181 --replication-factor 1 --partitions 1 --topic Kafka_Example`

## Consume from the Kafka Topic via Console
- `bin/kafka-console-consumer.sh --bootstrap-server localhost:9092 --topic Kafka_Example --from-beginning`

## Run the spring-boot application in linux from terminal 
- `mvn spring-boot:run`

## Publish message via WebService
- `http://localhost:8081/kafka/publish/Sam`
- `http://localhost:8081/kafka/publish/Peter`


## Issues with kafka: 
- `logs --> /root/programms/kafka_2.11-2.4.0/logs/server.log`

- `producerExample: https://github.com/kishoremarojuu/spring-boot-kafka-producer-example`
- `consumerExample: https://github.com/kishoremarojuu/spring-boot-kafka-consumer-example`


