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
