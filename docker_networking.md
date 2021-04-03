#list
docker network ls

#inspect
docker network inspect <network_name>

# inspect network of container
docker inspect <container_name>|<container_id>

# create network
docker network create --driver bridge <network_name>

# remove network
docker network rm <network_name>

#assign network for running container
docker network connect <network_name> <C_name>

