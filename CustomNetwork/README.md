# Set Custom Network for Services

- By default the network name will be folderName_default

- To define network im yml file, make network tag sibling of services (same indentation)

- Synatx will be:-
  
  _**networks:
      network_name:
        driver: driver_name**_

  - After defining the network, pass the network inside the services which we want.
 
<img width="918" alt="image" src="https://github.com/Shubham0315/dockerCompose/assets/105341138/3c061919-ad87-4ac1-8859-36128f597578">

  - As the network is defined in all services, containers of all services will communicate with each other using this network only.
  - If for any one of the service, we dont map container created, that service will create its own default network and will get tagged with it.

<img width="780" alt="image" src="https://github.com/Shubham0315/dockerCompose/assets/105341138/5eee7798-cbcb-4b42-a4c2-5e0e3f0e8359">



  
