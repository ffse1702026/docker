#list
docker ps

#list all
docker ps -a

#exit container and stop container
type: exit

#exit container and not stop container
type: Ctrl + P + Q

# run container
- docker run -it ubutu (run with terminal)
--name <Name>
-h <hostname>
-p <hostpost>:<container_port>
--rm (auto delete after stop)
--network <network_name> (start container with network)
-d chay nen`
-e (environmennt variable) ex: -e VA1=1 -e VAL2=2

run and copy file
docker run --rm -v <host_folder>:<contaner_foler> <image_name> cp <host_foler> <share_foler>

# start	container
docker start <container_name>|<container_id>

# stop	container
docker stop <container_name>|<container_id>

# open terminal if close
docker attack <container_name>|<container_id>

#delete container
docker rm <container_name>|<container_id>
docker rm -f <container_name>|<container_id> (remove running container)

#delete all docker container stop
docker container prune

#exec command to container from host machine
docker exec <container_name>|<container_id> <command>
ex: docker exec Ubutu ls
docker exec Ubutu bash : connect terminate

#save container to image
required: container exited
docker commit <container_name> <image_save_name>:<tag>

# copy file to container
docker cp <host_directory> <conatner_name>:/<container_directory>

# diff (start - now)
docker diff <container_name>|<container_id>

#show log
docker logs <container_name>|<container_id>
docker logs tail 10 <container_name>|<container_id>
docker logs -f <<container_name>|<container_id> (show log thoi gian thuc)

#check resouces
docker stats <container_name>|<container_id>



