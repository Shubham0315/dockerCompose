# Multiple Compose Files

- Sometimes there is a need of multiple compose files as we work on multiple environments.
- Suppose our "docker-compose.yml" file is for production. But we need another compose file for development.
  So create "docker-compose.dev.yml"

<img width="811" alt="image" src="https://github.com/Shubham0315/dockerCompose/assets/105341138/715a062e-0e21-4fd6-8bcd-4be655f38f5b">

# Run Custom Compose file

- Now to run the custom yml file, we need to pass -f flag in command
- If we run "docker compose up -d" it will take default yml file and will create and run the services of it

<img width="773" alt="image" src="https://github.com/Shubham0315/dockerCompose/assets/105341138/9cc0a598-0cc3-4332-9e5e-1398bcdc1c46">

- To remove/stop services

<img width="783" alt="image" src="https://github.com/Shubham0315/dockerCompose/assets/105341138/fdf7bf23-b20e-46e8-ad6f-5ba7386c90b7">


# Use Custom Imahe dockerfile within Compose file

- Create one simple dockerfile as below

<img width="497" alt="image" src="https://github.com/Shubham0315/dockerCompose/assets/105341138/33cd6227-1fa6-4318-9319-ec6bdd7b4780">

- Write one compose file and add service "build" as per below syntax

 _**app:
      build:
        context: contextPath
        dockerfile: Dockerfile**_

- In above syntax, after build also we can write "." so that it will fetch details of dockerfile from same location.
  Or we can provide dockerfile name as per last line of syntax

<img width="695" alt="image" src="https://github.com/Shubham0315/dockerCompose/assets/105341138/fc6226ad-158d-4851-97f9-a57af5213480">

- After running compose, we get below result as the compose file takes data from Dockerfile and build images and run containers for services

<img width="775" alt="image" src="https://github.com/Shubham0315/dockerCompose/assets/105341138/82714e43-4e7b-45a7-9554-7f0a0e4708b0">





