`Docker file ----> Build Image ----> Run Image ----> Container`
FROM node:alpine `Base Image: Version of Node`

WORKDIR /user/src/app `Create a directory in the container`

COPY . . `Copy all files from current directory to the container`

RUN npm install `Install all dependencies`

EXPOSE 3000 `Expose the port`

CMD ["npm","run", "start"] `Run the application`

//////////////////////////////////////////////////////////////////////////////////
Docker Commands
docker --version `Check the version of docker`
docker build -t <image-name> . `Build the image`
docker run --name <container-name> -p 3000:3000 <image-name> `Run the image along wwith port mapping`
docker ps `List all running containers`
docker images `List all images`
docker stop/kill <container-name> `Stop/kill the container`
docker rm <container-name> `removes the container`
docker run --name <contaner-name> -p 3000:3000 -v currenth project base path:/user/src/app <image-name> `Syncs the local project with the container/ Bind Mount`
Ex: docker run --name my-node-app-2 -p 5000:3000 -v C:\Users\saite\source\Docker_Demo:/user/src/app dockerdemoapp:v2
docker run --name <container-name> -p 3000:3000 -v /usr/src/app/node_modules -v $(pwd):/user/src/app <image-name> `Syncs the local project with the container and excludes the node_modules`
docker exec -it <container-name> sh `Access the container for windows`
docker build -t dockerdemoapp:v3 -f Dockerfile.dev . `Creates a build file from dev docker file for dev env`
docker exec -it my-node-app with-ignore sh
