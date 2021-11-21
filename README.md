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

# Enable the ability to discover microservices talking with EUREKA and using the name convention in Eureka http://localhost:8761 (e.g) CURRENCY-EXCHANGE
```spring.cloud.gateway.discovery.locator.enabled = true``` 
 
Allows to talk With Eureka and use the name of the application to go to the service through the name registered
e.g

Original URL --> ``http://localhost:8100/currency-conversion-feign/from/USD/to/MXN/quantity/10``

Using Spring Gateway --> ``http://localhost:8765/CURRENCY-EXCHANGE/currency-exchange/from/USD/to/MXN``

To avoid the upper case in the url add the following to properties

``spring.cloud.gateway.discovery.locator.lowerCaseServiceId = true``

Then...
Original URL --> ``http://localhost:8100/currency-conversion-feign/from/USD/to/MXN/quantity/10``

Using Spring Gateway --> ``http://localhost:8765/currency-exchange/currency-exchange/from/USD/to/MXN``
