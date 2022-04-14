# KAFKA API TO MONGO
1. prepare oracle server
```
cd oracle
docker-compose up -d
cd ..
```

1. start gravity, adapter, transmitterer
```
docker-compose up -d
```

2. test input data
```
docker exec -it oracle_oracle-xe-11g-r2_1 bash

sqlplus gravity/gravity

INSERT INTO users (ID, USERNAME, PASSWORD, NAME, EMAIL, PHONE, ADDRESS) VALUES ('54d7f5b9-ef1d-4ba0-8a54-f6000bbff427', 'JOSEWANG', 'q123456', 'JOSE', 'jose@gmail.com', '0987654321', 'asd');
```

3. check database
```
docker exec -it oracle_to_mongo_mongodb_1 bash

mongo
use gravity
db.gravity_vt.find({ID:"54d7f5b9-ef1d-4ba0-8a54-f6000bbff427"})
```
