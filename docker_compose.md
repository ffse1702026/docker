#version: "3"
# network
network:
  my-network:
    driver: bridge
	
#volumes
volumes:
  dir-site:
	driver_opts:
		device: /mycode/site/ (thu muc tren may host)
		o: bind
		
services: (caintainers)
	
	my-php:
		container_name: phh
		build: 
			dockerfile: Dockerfile
			context: ./php/ (noi chua docker file)
		hostname:php (host name)
		restart: always (auto restart)
		networks:
			- my-network (arr dung -)
		volumes:
			- dir-site:/home/sites/(map o dia)
			
	my-httpd:
		container_name: httpd
		image:"httpd:lastest"
		hostname:httpd (host name)
		restart: always (auto restart)
		networks:
			- my-network (arr dung -)
		volumes:
			- dir-site:/home/sites/(map o dia)
			- ./httpd.conf:/user
		ports:
			- "9999:80" 
			- "443:443" 

	my-sql:
		container_name: sql
		image:"sql:lastest"
		hostname:sql (host name)
		restart: always (auto restart)
		networks:
			- my-network (arr dung -)
		volumes:
			- ./mycf.conf:/user (map file)
			- ./db:/var
		ports:
			- "9999:80" 
			- "443:443" 
		environment:
			- MYSL_ROOT_PASSWORD=123456
			
			
# RUN
docker-compose up 

# remove
docker-compose down

# docker-compose ps
docker-compose ps

# stop
docker-compose stop

# start
docker-compose start

# restart
docker compose restart

# exec
docker-compose exec my-php bash

#logs
docker-compose logs <container_name>



