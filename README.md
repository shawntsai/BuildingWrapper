

# BuildingWrapper


Using inferlink to cluster similar web page and extract interesting information on the page

content can be ouput to csv, json file

### Prerequisites


```
python, scrapy, kafka, docker

```
get kafka from here

https://kafka.apache.org/intro

get docker from here

https://www.docker.com/


### Installing


```
pip install Scrapy
brew install kafka
```




```
➜  etc zookeeper-server-start kafka/zookeeper.properties                                          
➜  etc kafka-server-start kafka/server.properties        

➜  etc kafka-topics --create --zookeeper localhost:2181 --replication-factor 1 --partitions 1 --topic test
➜  craweling git:(master) ✗ kafka-topics --create --zookeeper localhost:2181 --replication-factor 1 --partitions 1 --topic review
```


- Configure landmark-compose/env/landmark-kafka-consumer.docker.env
- Change KAFKA_CONNECTIONS = public_IP:9092 (9092 is default port for
Kafka)
- Change KAFKA_CONSUME_TOPICS = topic_name
- Change KAFKA_SECURITY_PROTOCOL, KAFKA_SSL_CAFILE, KAFKA_SSL_CERTFILE, KAFKA_SSL_KEYFILE to nothing



- Run docker:
```
docker-compose up
```
- Send your CDR file to Kafka server:
```
kafka-console-producer.sh --broker-list localhost:9092 --topic
```
[topic_name] < your_cdr_path
o Other: bin/kafka-console-producer.sh --broker-list localhost:9092 --topic
[topic_name] < your_cdr_path

```
kafka-console-producer --broker-list localhost:9092 --topic test < YuHsiang_Tsai_cdr.jl
```




