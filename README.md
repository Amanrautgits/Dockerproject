# Dockerproject

Dockerize an application:-
 
 1. Created a project project .i.e react project
 2. Created a docker file for my project structure , where my source code is present.
 
 Docker file :-
 
#select image of node as base image version 22
FROM node:22-alpine
# create folder in container 
WORKDIR /app
COPY . .
RUN npm install
 #optional 
 EXPOSE 8000
 CMD [ "npm", "start"]

 
 
 3.docker build :- which will creates an image of your project structure.
 Docker build -t image_name .
 
 4.Created a tag for my image so that is can be 
 I.e docker tag react-with-docker:latest amanraut392/docker-images:latest
 
 5.docker login :- For accessing my docker hub so that we can push or pull the images in docker hub with username and password .
 
 6.Now ,pushing the docker image into docker hub , so that it can be stored in repository ,so that it can be properly managed.
 i.e docker push amanraut765/aman-docker-images:latest
 
 Pull to see if image has some changes in it if no changes then 
 :- Image is up to date for amanraut765/aman-docker-images:latest
 
 docker pull  amanraut765/aman-docker-images:latest
 
 7 . To run the docker image use .
 
 docker run -dp 3000:3000  amanraut765/aman-docker-images:latest
 So that we can access it using our localhost 
 Note :-  -d for detach mode and p is used for port mapping .
 Here i have find some of very usefull command for docker containers like 
 ->docker exec -it container_name sh/app
 ->docker logs container_id or docker logs -f container_id
 ->docker inspect container_id :- shows data in json format ,containers,networks,images.
