# MS-GeoLocation
This Microservice (simulates/produces) and sends messages to the ActiveMQ periodically. This is done by reading the GPX data of the route I captured with Strava.

## Getting Started
This Microservice is a simple Spring-Boot application with a single configuration file in form of application.properties

### Prerequisites

```
We have to clone this repository preferably inside a seperate workspace folder for STS/Eclipse IDE.
this helps running each application indifferent instances of IDE and manage start/stop of the application 
in a seperate JVM.
```

### application.properties
This needs URL of a Messaging QUEUE that we can have independent running and not a Spring-Boot embedded one.
```
spring.activemq.broker-url=tcp://localhost:61616
```

## Dependencies
```
<groupId>org.springframework.boot</groupId>
<artifactId>spring-boot-starter-activemq</artifactId>
```

## Development 

We are reading GPX data (lat="48.0865250" lon="11.5978280") from a text file with a scanner and we run that in a loop to send to Message broker.
by creating a ConcurrentHashMap and USE JmsTemplate class from Spring to use convertAndSend() to send a JMS MAP message to the Broker.

## Built With

* [Spring-Boot 1.5](http://start.spring.io/) - The Service Templating tool in Spring Microservice world by Pivotal.
* [Maven](https://maven.apache.org/) - Dependency Management

* **vimal krishna** - *Initial work* 
