# REST API TO MONGO
1. start gravity-adapter-rest
```
docker-compose up -d
```

2. test input data
```
curl -X POST http://localhost:8080/dataInput -H 'Content-Type: application/json' -d '{"event":"rowCreate","payload":{"ID":"54d7f5b9-ef1d-4ba0-8a54-f6000bbff417","USERNAME":"JOSEWANG","PASSWORD":"password","NAME":"JOSE","EMAIL":"jose@gmail.com","PHONE":"0987654321","ADDRESS":"ABCCC"}}'
```

3. check database
```
docker exec -it oracle_to_mongo_mongodb_1 bash

mongo
use gravity
db.gravity_vt.find({ID:"54d7f5b9-ef1d-4ba0-8a54-f6000bbff417"})
```
