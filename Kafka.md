#Kafka

###Start
1.first start zookeeper
commad: zookeeper-server-start.sh config/zookeeper.properties
2.start kafka
commad: kafka-server-start.sh config/server.properties

### create topic
commnad: kafka-topics.sh --create --zookeeper localhost:2181 --replication-factor 1 --partition 1 --topic test
list command: kafka-topics.sh --list --zookeeper localhost:2181

###send message
command: kafka-console-producer.sh --broker-list localhost:9092 --topic test

###consume message
command : kafka-console-consumer.sh --bootstrap-server localhost:9092 --topic test --from-beginning 
