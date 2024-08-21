# Microservice App - PRFT Devops Training

This is the application you are going to use through the whole traninig. This, hopefully, will teach you the fundamentals you need in a real project. You will find a basic TODO application designed with a [microservice architecture](https://microservices.io). Although is a TODO application, it is interesting because the microservices that compose it are written in different programming language or frameworks (Go, Python, Vue, Java, and NodeJS). With this design you will experiment with multiple build tools and environments. 

[Click here to know how to run it!](#how-to-run)

## Components
In each folder you can find a more in-depth explanation of each component:

1. [Users API](/users-api) is a Spring Boot application. Provides user profiles. At the moment, does not provide full CRUD, just getting a single user and all users.
2. [Auth API](/auth-api) is a Go application, and provides authorization functionality. Generates [JWT](https://jwt.io/) tokens to be used with other APIs.
3. [TODOs API](/todos-api) is a NodeJS application, provides CRUD functionality over user's TODO records. Also, it logs "create" and "delete" operations to [Redis](https://redis.io/) queue.
4. [Log Message Processor](/log-message-processor) is a queue processor written in Python. Its purpose is to read messages from a Redis queue and print them to standard output.
5. [Frontend](/frontend) Vue application, provides UI.

## Architecture

Take a look at the components diagram that describes them and their interactions.
![microservice-app-example](/arch-img/Microservices.png)

## How to run
To run this project you need to have docker compose and docker installed on your deploy environment. Whether it is your own OS, WSL2, Virtual machine, etc.
### 1. Clone the project and move into the created folder
```console
foo@bar:~$ git clone https://github.com/G-Delgado/microservice-app-example.git
[/////    ]  cloning process 
```
```console
foo@bar:~$ cd microservice-app-example
foo@bar:./microservice-app-example$ 
```

### 2. On that folder run docker compose
```console
foo@bar:./microservice-app-example$ docker-compose up -d
[/////    ]  starting services
```

Then, wait for all the services to start. If you have any issues relating ports or services already running, kill the processes running on those ports.

### Enjoy!
You should have your microservices all set up and running
