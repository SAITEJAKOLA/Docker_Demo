`Docker file ----> Build Image ----> Run Image ----> Container`
`Base Image: Version of Node`
FROM node:alpine 
`Create a directory in the container`
WORKDIR /user/src/app 
`Copy all files from current directory to the container`
COPY . . 
`Install all dependencies`
RUN npm install 
`Expose the port`
EXPOSE 3000 
`Run the application`
CMD ["npm","run", "start"] 

//////////////////////////////////////////////////////////////////////////////////
Docker Commands
`Check the version of docker`
docker --version
`Build the image`
docker build -t <image-name> . 
`Run the image along wwith port mapping`
docker run --name <container-name> -p 3000:3000 <image-name> 
`List all running containers`
docker ps 
`List all images`
docker images 
`Stop/kill the container`
docker stop/kill <container-name> 
`removes the container`
docker rm <container-name> 
`Syncs the local project with the container/ Bind Mount`
docker run --name <contaner-name> -p 3000:3000 -v currenth project base path:/user/src/app <image-name> 
`Ex: docker run --name my-node-app-2 -p 5000:3000 -v C:\Users\saite\source\Docker_Demo:/user/src/app dockerdemoapp:v2`
`Syncs the local project with the container and excludes the node_modules`
docker run --name <container-name> -p 3000:3000 -v /usr/src/app/node_modules -v $(pwd):/user/src/app <image-name> 
`Access the container for windows`
docker exec -it <container-name> sh 
`Creates a build file from dev docker file for dev env`
docker build -t dockerdemoapp:v3 -f Dockerfile.dev . 
