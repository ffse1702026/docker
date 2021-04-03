#FROM <Image name>

# thi hanh lenh
RUN yum install -yum
RUN yum install httpd

# run coppy
ADD ./test.html /opt/html

# thu muc lam viec mac dinh cua image
WORKDIR /var/html

# port cua image
EXPOSE 80:80

#chay tien trinh build xong
ENTRYPOINT ["httpd"]
CMD ["-D", "FOREGROUND"]



#build
Docker build -t <imageName>:<tag> -f Dockerfile .
