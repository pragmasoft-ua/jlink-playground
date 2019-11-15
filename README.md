# jlink-playground
Playground project of minimized packaging of spring boot application

## Build

`./mvnw clean package jib:dockerBuild`

## Docker run postgres

`docker volume create pgdata`

`docker network create jlink`

`docker run -d --name postgres -p 5432:5432 -v pgdata:/var/lib/postgresql/data -e POSTGRES_PASSWORD=pgpa55word --network jlink postgres:11`

## Docker run

`docker run -it --rm --name greeter -p 80:8080 --network jlink -e RDS_HOSTNAME=postgres 488285037276.dkr.ecr.us-east-1.amazonaws.com/air/greeter`

## Push

`./mvnw clean package jib:build`

## TODO

AWS config rules
CDK
https://habr.com/ru/company/hh/blog/450954/
Git info/plugin

## AWS Infrastructure

1. IAM roles
2. ssh keys
3. VPC
4. subnets
5. NAT
6. ECR repo

