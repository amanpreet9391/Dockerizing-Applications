## Node + Redis --> NodeWebApp
A node web app that can be accessed through browser and which shows count for the number of time the web page is visited. </br>
In this we used `docker-compose` to create containers for node-app and redis.</br>
## Steps
* Create a dockerfile for node-app and create its image</br>
* Use the official image of redis.
* Create their containers and connect them using docker-compose.
To build and run docker-compose, run command `docker-compose up` . The service will be up and running and can be accessed on the browser on `http://localhost:4001`.