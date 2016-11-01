

1. cql schema:

CREATE KEYSPACE voting
    WITH REPLICATION = {
        'class' : 'SimpleStrategy',
        'replication_factor' : 1
    };
 
USE voting;
 
CREATE TABLE votes (name text PRIMARY KEY, votes int);

2. Kafka


cd /Users/kevinwu/Documents/zw_progs/kafka/kafka_2.11-0.8.2.1

bin/kafka-topics.sh --zookeeper localhost:2181 --create --topic votes --partitions 1 --replication-factor 1


bin/kafka-console-consumer.sh --zookeeper localhost:2181 --topic votes --from-beginning


--create:
  bin/kafka-topics.sh --create --zookeeper localhost:2181 --replication-factor 1 --partitions 1 --topic votes

--list:
  bin/kafka-topics.sh --list --zookeeper localhost:2181

--delete:
  bin/kafka-topics.sh --zookeeper localhost:2181 --delete --topic votes

3. Sample message in the Kafka Producer
{"kevin"}
{"alice"}
{"kevin"}
