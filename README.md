# dockerCompose

- Docker compose is a tool for defining and running multi-container Docker apps. Multi container applications means they need different images to run applications.
- With compose we write YAML file to configure your apps services.
- With a single command we can create and start all the services from our configuration.
- Compose works in all environments : prod, staging, dev, testing as well as CI workflows.
- Docker desktop includes Docker compose along with docker engine and docker CLI which are compose prerequisites
e.g:- Suppose we need multi module application consisting of python, mysql, redis to run app. So we need to pull images for all of them and run containers for them and manage these containers. This is made easy by "Docker compose".

# Use cases of Docker Compose
- To make development env
- To make automated testing env
- Single host deployments

# Key Features
- Have multiple isolated environments on single host
- Preserves volume data when containers are created. We can use same volume for different environments
- Only recreate containers that have changed (yaml files changed)
- Supports variables and moving a composition between environments

# Basic Compose Commands
1. docker compose up
- Takes input from _**docker-compose.yml**_ file and starts building container. It downloads/pulls required images and create/start required containers. If we modify the yml and again run docker compose up, it will recreate modified containers. This fastens performance of container

2. docker compose up -d
- Same as docker compose up but it will run in background which means it wont occupy terminal (detached mode)

3. docker compose ps
- To list currently running services

4. docker compose stop
- Used to stop compose started using docker compose up -d

5. docker compose down
- Used to remove containers entirely. It wont remove volumes. To remove volumes use --volumes flag



