# Depends On Feature

- This feature is used to set order of container creation and removal (Startpu and Showdown order).
- We can make containers dependent on each other.

- Pass the "depends on" tag inside one service and make the service dependent on other services

<img width="933" alt="image" src="https://github.com/Shubham0315/dockerCompose/assets/105341138/1f0799bd-f6a1-40a5-a51f-b6914b896b91">

- After running compose up -d, the container will ge created in specified order.

<img width="775" alt="image" src="https://github.com/Shubham0315/dockerCompose/assets/105341138/1f721f9a-3a78-4152-9253-0e37940094ce">

