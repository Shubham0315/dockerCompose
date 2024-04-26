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
