Explain Docker compose with its features
-
- Docker compose is a tool that helps you define and manage multi-container docker apps. Instead of running multiple docker run commands we can use single docker-compose.yml file to define networks, services and columes in a structured way
- Why use Compose?
  - Simplifies multi container app deployment
  - Provides single config file for managing containers
  - Allows scalability, networking and volume management
  - Supports env variables and secret management
 
- **_Features of Docker compose_**
  - **Multi container management** :- We can define and manage multiple containers in one docker-compose.yml file. Here we define services and images used for those.
 
  ![image](https://github.com/user-attachments/assets/914dbc41-7e51-4ac5-930a-3b0c8e2c0fad)

  - **Environment variable management** :- We can pass env variables directly or from .env file
  - **Scaling services** :- docker compose up --scale web=3      #launch 3 insteances of service "web" for LB
  - **Build custom images** :- Instead of using prebuilt image we can specify dockerfile to build custom image
  - **One Command deployment** :- docker compose up -d / down -d
 
- Docker compose simplifies multi container apps by defining services in single yaml file, managing networks and volumes
- With single compose command we can create and start all services in our yml file(coonfig)
- It works in all env like dev, staging, prod, testing

---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Explain docker-compose.yml file
-
- It is a config file used by docker compose to define and manage multi-container apps. It describes services, networks and volumes required to run app.

- Structure of compose file
  - version :- to define compose version. Version of compose file format 
  - services :- to define names of containers and inside services we can define images used for the containers
  - networks :- used for communication between 2 services
  - volumes :- for persistent storage

![image](https://github.com/user-attachments/assets/8789e418-246a-4d65-8091-df6bfcdf7063)

- In above image nginx image is used to run service named "web" which is the container

- Using compose, we can do building images, creating containers and starting them in one command

---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Explain docker compose commands to start services
-
1. Write docker compose file with the required services and tag images

 ![image](https://github.com/user-attachments/assets/dd899e5d-154d-4f38-99b6-97f886af9324)

2. To check what's in our yml file :- **docker compose config**
  - Here name is folder name where our yml file is. It displays services with images. It will show the default network if not specified (folderName_default)
 
![image](https://github.com/user-attachments/assets/94301d3f-5a44-4e86-8cf5-e82105dbffd4)

  - As per above, 2 containers for nginx and redis will be created and will communicate with each other using default network

3. Now to create and start containers, run below in folder where our yml file is present
  - Command :- **docker compose up -d**
  - Here we can see default network is also created along with 2 containers. If image is not present in local, it will fetch the same from dockerhub and provide in output
  - here container names will also be in below format :- **folderName_serviceName**
 
![image](https://github.com/user-attachments/assets/7ab867a7-e317-44c6-8fae-6a957d50c068)

4. To check containers created using commands
  - Command :- **docker container ls / docker compose ps**
  - This command gives containerID, name, created time, status, port

![image](https://github.com/user-attachments/assets/85180380-f6f7-4769-a035-0200980ff66a)

5. To check other asepcts in compose file
  - To check networks and driver/scope associated :- **docker network ls**
  - To check volume :- **docker volume ls**
  - To go inside container :- **docker compose exec $serviceName bash**
  - To stop container :- **docker compose down --volumes**

![image](https://github.com/user-attachments/assets/5b28c6b5-39d0-4c50-acc8-12aa629ac9c0)
![image](https://github.com/user-attachments/assets/781d32de-e030-4d52-af65-d13bc80f8986)

---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Explain use of environment variable in docker compose
-
- Environment variables in docker compose allow you to configure services dynamically, avoid hardcoding sensitive data and manage different environments (dev, test, prod)
- Ways to define Env variables in compose :- directly in yml file, use external .env file, pass them from CLI

- As we can pass env variables in .env files in same location as yml file is. Lets pass redis TAG in .env and use mysqlconfig.env file to pass db password

![image](https://github.com/user-attachments/assets/46d02cf5-2bd3-473c-959b-382115102fe1)

- Otherwise we can also pass env variable inside the service as below inside environment section

![image](https://github.com/user-attachments/assets/7afd36a3-549a-4478-a8c9-8ef9b504bf27)

- Another way is like below, pass the password in another file .env:-
  db:
    image: mysql
    environment:
      MYSQL_ROOT_PASSWORD: ${MYSQL_ROOT_PASSWORD}

- .env file  keeps our credentials secure and we can easily change values without modifying docker-compose.yml

- Also we can run below command :- **docker compose --env-file $Custom.env up -d**

---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

How to set profile for a particular service in docker compose
-
- Docker compose profiles allow you to enable or disable specific services when running docker compose up. This is useful when we have different environments and want to control which service to run
- If we've 3 services in our yml file and we want only 1st and 3rd to be enabled, we can set profile for that service
- We can define profile for a service using profiles key as by default all services in yml are enabled when we run docker compose. Even if we check config it shows only 2 services enable by default.

![image](https://github.com/user-attachments/assets/94986910-8eb6-4f41-b869-cf98a617a74f)

- To view config files which're not enabled by default, provide service name using --profiles flag

![image](https://github.com/user-attachments/assets/97c14d00-5da5-4ac4-ba7f-3c0800292afa)

- If we run docker compose up -d, it will create and start services enabled by default

![image](https://github.com/user-attachments/assets/c9f8fc7f-cb0a-470d-bcc6-5f6b8d29b4b8)

- To start and run the container of service which is set to profile, we cna mention that service in CLI
  - Command :- **docker compose --profile rediscache up -d**

![image](https://github.com/user-attachments/assets/691669cf-7b29-497e-9400-ed1bfc59d995)

- Benefits of Using Profiles:-
  - Selective startup order
  - Improved performance as it avoids running unnecessary containers
  - Better env management

---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
