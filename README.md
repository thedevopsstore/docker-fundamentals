# Docker Fundamentals

## What is covered as part of Docker Fundamentals?
1. Docker Introduction
2. Docker Installation
3. Flow-1: Pull from Docker Hub and Run Docker Image locally.
4. Flow-2: Build new Docker Image and Run locally and Push to Docker Hub.
5. Essential Docker Commands

## What is Docker ?

Its a container runtime which does the below 

1. Images: It aids you in packaging an application (with *all* its dependencies).
2. Registries: It helps to distribute that app around to all the places you need to run it.
3. Containers: It runs that app in a highly reproducible way.

Docker calls this the "Build, Ship and Run" lifecycle.

### The Docker Image:

1. It’s called a "Docker image" or just "image" for short.
2. Docker uses a list instructions, called a Dockerfile, which is similar to a shell script, and it layers those instructions on top of each other until it has everything you need to run the application, including all its system dependencies.
3. Including the dependencies is a key differentiator between Docker and many previous packaging systems. It helps prevent the (only) "works on my machine" problem of two different environments having slightly different sets of dependencies.
4. If it was a Nodejs app you wanted to build, then the image would contain the app itself, all the Node dependencies the app needs.
5. They key distinction is it also include the exact Node version and system libraries to correctly run Nodejs.
6. Everything except the OS kernel and hardware drivers is included. Even metadata on how to start the app, default environment variables, and what ports it listens on are included.


### The Registry:


1. Called a "Docker registry", or just "registry" for short.
2. Now that we have built an image, ran it on our local machine, how do we get it on all the other machines?
3. How can I be sure that the rest of my team, my CI testing, and all my servers run the exact same image?
4. The registry is a HTTP-based package manager that works like apt, yum, npm, and other package managers.
5. You can *push* an image to it, and then *pull* an image somewhere else.


> Think of the images and the registry as the universal package manager for modern computing, where we may want to build, download, and run any app on any system. 

### The Docker Container:



 1. Called a "Docker container", or just "container" for short. 
 2. Docker will launch your container image into a new running container and use the command you specified in the Dockerfile to start it.
 3. You can start many of these containers from the same container image, on the same system, and they’ll all be isolated from each other. File changes in one container don’t affect the files in another.

