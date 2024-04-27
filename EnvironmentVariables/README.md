# Environment Variable

1. We can pass environment variables in .env files in same location as yml file
  Lets, pass TAG of redis in .env instead of yml. So .env and yml files will look like below:-

<img width="920" alt="image" src="https://github.com/Shubham0315/dockerCompose/assets/105341138/8af1a782-d833-4e4f-b86a-0f7fa5eecdcc">
<img width="578" alt="image" src="https://github.com/Shubham0315/dockerCompose/assets/105341138/29e42e1e-30ab-4a1e-881a-96143cfd73fc">

2. Set environment attribute in Service container
- Inside service container, provide environment attribute (environment:) and provide name=value of attribute as below (password). We have provided attribute in array format, which can also be defined in map format as commented out in snap.
- Also we can define attribute in .env and pass the same in yml file as below snap.

<img width="923" alt="image" src="https://github.com/Shubham0315/dockerCompose/assets/105341138/75e2ddae-fc06-4eca-a352-4cbd5b0c4412">
<img width="590" alt="image" src="https://github.com/Shubham0315/dockerCompose/assets/105341138/2f1ab360-23cc-444d-a703-d973bea3544f">


From below snap, we can see one application in running state which have 3 containers in it and also lists config file (yml)

<img width="781" alt="image" src="https://github.com/Shubham0315/dockerCompose/assets/105341138/96c3e39c-0d67-4737-abda-e3b3f3df2af5">

3. Using environment file in service container
- We can create one file for PASS like "mysqlconfig.env" and define the password there and pass the same in yml file using env_file tag as below

<img width="733" alt="image" src="https://github.com/Shubham0315/dockerCompose/assets/105341138/8de1c6b2-f97c-42e3-9174-56cfb1b0ef3e">
<img width="533" alt="image" src="https://github.com/Shubham0315/dockerCompose/assets/105341138/228a7ba3-a61f-4fee-86cb-5ac387b872e4">



