# list
docker images

#search
docker search <image_name>

#pull
docker pull <image_name>:<tag>

#remove images
docker image rm <image_name>|<image_id>

# run image
docker run <Option> <image_name>
- docker run -it ubutu (run with terminal)

# save image to file
- docker save --output <filename.tar> <id_image>|<image_name>

#load image
- docker load -i <filename.tar>

# set name image
docker tag <image_id> <name_image>:<image_tag>

#history image
docker image history <name_image>:<image_tag>

# inspect image
docker inspect <name_image>:<image_tag>