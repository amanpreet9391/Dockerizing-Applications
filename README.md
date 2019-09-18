## Dockerizing simple applications
In this repository we containerised two applications: </br>
1. Simple web server using flask </br>
2. Simple Node-app with Redis </br>
While dealing with docker, sometimes we use the official images uploaded on dockerhub and sometimes we create our own image according to the requirement.</br>
To create your own image, follow these steps: </br>
* Create Dockerfile.
* Add source code
* Run `docker build` command </br>
To check the created image run `docker images` command. Image can also be tagged or given a name using command `docker build . -t name`.
