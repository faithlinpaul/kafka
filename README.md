# kafka
kafka notes

Producer-Consumer model

1. Topics to subscribe
2. Grouping of Consumers
3. Replicate Brokers using Mirrormaker

Tools:
Mirrormaker, Zookeeper, 

SQS v activemq v rabbitmq v kafka (batch 50) v kafka (batch 1) 

Use cases:
----------
1. Website analysis
2. Operations metrics
3. Log aggregation
4. Stream processing
5. Event sourcing

Commands:
---------

bin/zookeeper-server-start.sh config/zookeeper.properties  
 
bin/kafka-server-start.sh config/server.properties 
 
bin/kafka-create-topic.sh --zookeeper localhost:2181 --replica 1 --partition 1 --topic test 
 
bin/kafka-list-topic.sh --zookeeper localhost:2181 
 
bin/kafka-console-producer.sh --broker-list localhost:9092 --topic test  
Hello World  
Hello Kafka  
 
bin/kafka-console-consumer.sh --zookeeper localhost:2181 --topic test --from-beginning  
Hello World  
Hello Kafka
 
 
