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

1. IAM roles - service, instance
2. ssh key
3. VPC
4. subnets, internet gateway, default route to gw in public subnet
5. NAT instance - source/destination check, default route to nat in private subnet
6. ECR repo
7. S3 bucket for access logs - bucket policy
8. us-east-1e does not support t3.xxx instances

