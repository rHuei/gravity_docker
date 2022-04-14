# KAFKA API TO MONGO
1. prepare kafka server
```
cd kafka
docker-compose up -d
cd ..
```

1. start gravity-adapter-kafka
```
docker-compose up -d
```

2. test input data
```
docker exec -it kafka_kafka_1 bash

kafka-console-producer.sh --bootstrap-server kafka:9092 --topic gravity

{"event":"rowCreate","payload":{"ID":"54d7f5b9-ef1d-4ba0-8a54-f6000bbff412","USERNAME":"JOSEWANG","PASSWORD":"password","NAME":"JOSE","EMAIL":"jose@gmail.com","PHONE":"0987654321","ADDRESS":"ABCCC"}}
```

3. check database
```
docker exec -it oracle_to_mongo_mongodb_1 bash

mongo
use gravity
db.gravity_vt.find({ID:"54d7f5b9-ef1d-4ba0-8a54-f6000bbff412"})
```
