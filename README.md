# api-gateway
Project to implement Spring Cloud Gateway instead of Zuul, for UDEMY Microservices Course

# Initial structure of the project
![image](https://user-images.githubusercontent.com/36638342/142779422-5eac5803-aaa2-4bc7-b913-c5c2e9948a0e.png)

# Spring Cloud Gateway to use the same common configuration between microservices
- In a typical Microservices architecture there are a lot of microservices (hundreds, thousands)
- A lot of them share common configurations
- Spring Cloud API Gateway does that work for you
    - In Earlier versions of Spring was called Zuul

Is registered automatically in Eureka, but to be sure, you can configure the properties file
``eureka.client.serviceUrl.defaultZone = http://localhost:8761/eureka``
![img.png](img.png)