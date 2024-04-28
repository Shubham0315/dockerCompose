# Expose Ports to Service

- To expose port tp nginx service in yml file, add ports inside the "nginx" service. Map the host port (8081) to container port (81).

<img width="911" alt="image" src="https://github.com/Shubham0315/dockerCompose/assets/105341138/6e0c5a4a-ea28-43da-b70f-40041615cc07">

After adding port, run docker compose up

<img width="782" alt="image" src="https://github.com/Shubham0315/dockerCompose/assets/105341138/fcbede77-5983-459f-8027-5b6a85cb5990">

- Now to check ports mapped to service, run "docker ps -a". 0.0.0.0 means any IP with port mapped.

<img width="779" alt="image" src="https://github.com/Shubham0315/dockerCompose/assets/105341138/0a659248-81fc-4102-bcf5-82f1ada175b8">


