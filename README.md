# springboot-microservices-suite
This repo shows how to implement microservices components using Spring Boot

## Microservices

1. naming-server - This service ats as Eureka Server 
2. currency-conversion-service - This microservice is used for currency conversion
3. currency-exchange-service - This microservice provide currency exchange rate interacts with the database and provides currency exchange rate to currency conversion service

## Microservices Components

- Feign Client - It is is a declarative REST client which is used to call other microservices. This is a great alternative for RESTTemplate() API.
- Eureka Server - This is a discovery server where microservices can register themselves so others can discover them. Usage is Feign Client is very convenient because of Eureka server as you just provide the name of service to connect in Feign Client. 
- Eureka Client - Mostly it is a microservice that registers itself to the Eureka server
- Eureka Instance - a single instance of a microservice (you can add more instances of the same microservice as your load grows i.e. horizontal scaling).

