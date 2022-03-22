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
- Load Balancing - With new updates in Spring Cloud, Load balancing can be achieved with a combination of Feign Client and Eureka Server interaction. This is also called as Client kside load balancing.
- Spring Cloud API Gateway - This is a new API in Spring Cloud which provides out-of-the-box routing mechanisms often used in microservices applications as a way of hiding multiple services behind a single facade.
- Circuit Breaker 
  - One Microservice may call other, and that one may call another microservice. It may form a long chain of interaction between microservices.
  - In such cases, if one of the microservice fail, then it will have an impact on other microservices that call it, and will have a domino effect.
  - To mitigate such situation, we apply Circuit Breaker mechanism.
  - In the circuit breaker, there are 3 states Closed, Open, and Half-Open : 
    - Closed: when everything is normal. Initially, the circuit breaker is in a Closed state.
    - Open: when a failure occurs above predetermined criteria. In this state, requests to other microservices will not be executed and fail-fast or fallback will be performed if available. When this state has passed a certain time limit, it will automatically or according to certain criteria will be returned to the Half-Open state.
    - Half-Open: several requests will be executed to find out whether the microservices that we are calling are working normally. If successful, the state will be returned to the Closed state. However, if it still fails it will be returned to the Open state.

