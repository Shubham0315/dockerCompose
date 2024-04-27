# Creation of yaml file
Supoose our application needs creation of multiple containers like nginx, redis and mysql.
All of these can be created manually and we can run containers after building individual images.

- Using compose, we can do building images, creating containers and starting them in one command

  In yaml file, write services needed and tag images for each of the service as below

<img width="930" alt="image" src="https://github.com/Shubham0315/dockerCompose/assets/105341138/101d25a4-08b8-4529-9a78-764e6d1534a7">

_**Command :- docker compose config**_  :- Shows what's in our yaml file. Name is folder name where yaml file is. Displays services with images. Network will be default if not specified (folderName_default)

<img width="761" alt="image" src="https://github.com/Shubham0315/dockerCompose/assets/105341138/5000450e-62a6-4c03-b5a6-4dddcbbe043c">

As per above image, 2 containers will be created for 2 images and both will be connected to each other through default network.

Now, to create and start containers
_**Command :- docker compose up -d**_   (in folder where default docker-compose.yml is present)

<img width="779" alt="image" src="https://github.com/Shubham0315/dockerCompose/assets/105341138/8fd5cca4-d969-453a-9728-4879a73625fb">

If image is not present in local, it will fetch the same from dockerhub and provide in output. The output will consist of containers built from images and default network.

Container name will be folderName_serviceName

We can also check the images, containers and network associated are create or not in docker desktop.

<img width="959" alt="image" src="https://github.com/Shubham0315/dockerCompose/assets/105341138/23e99fe9-d178-4498-b67d-3b62e50437b1">

1. To check containers created using commands

_**Command :- docker container ls**_  :- Gives containerID, Image name, Created time, Status, Ports (Ports will be default ones of the container)
OR
_**Command :- docker compose ps**_

<img width="782" alt="image" src="https://github.com/Shubham0315/dockerCompose/assets/105341138/4bbc3502-0f4a-4516-9b72-5e68d70c355f">

2. To check networks created

_**Command :- docker network ls**_  :- Gives network ID, Name, Driver, Scope

<img width="775" alt="image" src="https://github.com/Shubham0315/dockerCompose/assets/105341138/e406c41a-eca1-474e-b7fb-fcd5bbdd66de">

3. To check volumes

_**Command :- docker volume ls**_  :- Gives Driver and Volume name

4. To go inside container

_**Command :- docker compose exec serviceName bash**_  :- Go inside nginx service





  
