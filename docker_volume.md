# run container with share volume host
docker run --it -v <pathHost>:<pathContainer> <imageid>|<image_name>

# run container with share beetween container
docker run --it --name <container_name> --volumes-from <container_name_sharing> <imageid>|<image_name> 

# list disk in docker
docker volume ls

#create disk
docker volume create <volume_name>

# check disk
docker volume inspect <volume_name>

# remove disk
docker volume rm <volume_name>

# assign disk to container
docker run --it --name <C_name> --mount source=<dis_name>,target=<container_directory> <image_name>

# create volume anh xa host
docker volume create --opt device=<host_foler> --opt type=none o=bind <volume_name>

# assign volum anh xa
docker run --it --name <C_name> -v=<dis_name>:<container_directory> <image_name>
