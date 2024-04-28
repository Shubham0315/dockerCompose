# Set profiles for Services

- By default all the services defined in yml file are enabled. So when we run "docker-ompose up -d", all services start running.
- But if we want a specific service to be enabled and running only after we provide input, we can set profile to that service/

In below snap, the profile is set for redis service.

<img width="788" alt="image" src="https://github.com/Shubham0315/dockerCompose/assets/105341138/79b9f88c-3342-4f6a-a5a8-1f2c715959c3">

- Even if we check config for compose file, it shows only two services which are enabled by default.

<img width="780" alt="image" src="https://github.com/Shubham0315/dockerCompose/assets/105341138/7396492a-f206-43b7-a417-fff6e0183c12">

- To view config of the services which are not enabled by default, provide the service name using --profiles flag

_**Command :- docker compose --profile rediscache config**_

<img width="779" alt="image" src="https://github.com/Shubham0315/dockerCompose/assets/105341138/5c780dfc-7b28-4106-a490-ae66b8bab292">

If we run "docker compose up -d", it will start and run only services which are enabled by default

<img width="766" alt="image" src="https://github.com/Shubham0315/dockerCompose/assets/105341138/2584345e-9300-43e6-b15a-80802394c7c6">

To start and run container of the service which is set to profile, we can mention that service explicitly

_**Command :- docker compose --profile rediscache up -d**_

<img width="776" alt="image" src="https://github.com/Shubham0315/dockerCompose/assets/105341138/2037255f-13a0-411d-910b-01a73feaa276">


- When we try to remove the containers now using "docker compose down --volumes", it throws below error :- Resource Still in use"
  This is due to our network is associated with redis profile as well. So that profile also needs to be passed. Until redis container is running, our network will be there.

  <img width="773" alt="image" src="https://github.com/Shubham0315/dockerCompose/assets/105341138/178f0604-5925-406f-b37c-9f220a430ccd">





