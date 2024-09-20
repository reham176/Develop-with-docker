## start mongodb
 docker run -d \
--name mongodb \
--net mongo-network \
-e MONGO_INITDB_ROOT_USERNAME=admin \
-e MONGO_INITDB_ROOT_PASSWORD=password \
-p 27017:27017 \
mongo



## start mongo-express
docker run -d \
--name mongo-express \
-p 8080:8081 \
--net mongo-network \
-e ME_CONFIG_MONGODB_ADMINUSERNAME=admin \
-e ME_CONFIG_MONGODB_ADMINPASSWORD=password \
-e ME_CONFIG_MONGODB_SERVER=mongodb \
mongo-express