# docker-help

Install Docker in Ubuntu : https://phoenixnap.com/kb/how-to-install-docker-on-ubuntu-18-04

==== see All Docker Images available and delete some =====  
sudo docker images  
sudo docker rmi 2f 69 [remove images 2f and 69 are the starting hash of images]  

==== when you have multiple contaners [weapp, db etc] -----  
docker-compose file will be used to define.  
docker-compose up   [to start docker image]  

 
====== Build a Image and Push to Hub ==========  
sudo docker login --username=bijeesraj007 [Login to docker hub from terminal, so that you an push the image]  
docker build -t bijeesraj007/shop:latest . Build and Tag with name 'bijeesraj007/shop:latest' make sure to be in the location where dockerfile is located . sm-shop]  
docker build .    [generic build command]  
docker push bijeesraj007/shop:latest  [To push a created image to docker hub where bijeesraj007/shop is the image name]  


======= Run a Docker Image =====  
sudo docker login --username=bijeesraj007 [Login to docker hub from terminal, so that you an pull the image]  
sudo docker pull bijeesraj007/shop:latest   [Pull an image]  
docker run -d -p 8080:8080 bijeesraj007/shop  [bijeesraj007/shop  is the image name. Bind Systems 8080 port to docker containers 8080 port, run in background]  
Or docker run -d -p 8080:8080 68   [where 68 is the first few bytes hash of the image]  


==== Watch the logs ===  
sudo docker ps   [get start of running container and get the hash]  
sudo docker logs -f 37  [where 37 is the fist few chars of hash]  

=== Building image of a Spring boot app and Run it ==  
docker build -t docker-demo-app-1.0.jar .
docker image ls
docker run -p 9090:8080 docker-demo-app-1.0.jar
