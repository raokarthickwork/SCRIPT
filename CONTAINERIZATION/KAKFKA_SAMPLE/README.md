## Run the docker-compose file as below
```
docker-compose up -d
```

### Find the docker-id from the command
```
docker ps
```

## Run the producer
```
docker exec -it <kafka-container-id> /opt/kafka/bin/kafka-topics.sh --create --zookeeper zookeeper:2181 --replication-factor 1 --partitions 1 --topic my-topic
```

## Run the consumer
```
docker exec -it <kafka-container-id> /opt/kafka/bin/kafka-console-consumer.sh --bootstrap-server localhost:9092 --topic my-topic --from-beginning
```

## Stop the docker-compose
```
docker-compose down
```