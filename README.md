# jlink-playground
Playground project of minimized packaging of spring boot application

## Build

`./mvnw clean package jib:dockerBuild`

## Docker run

`docker run -it --rm --name greeter -p 80:8080 488285037276.dkr.ecr.us-east-1.amazonaws.com/air/greeter`

## Push

`./mvnw clean package jib:build`