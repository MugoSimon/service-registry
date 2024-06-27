# Service Registry (Eureka Server)

The Service Registry, also known as the Eureka Server, is responsible for service discovery and registration in the microservices architecture.

## Features
- Provides a centralized service registry where all microservices can register themselves
- Allows clients (microservices) to discover the location and availability of other services
- Supports high availability through peer awareness and self-preservation mode

## Configuration
The Eureka Server requires the following configuration:

```properties
# Eureka Server Configuration
eureka.client.register-with-eureka=false
eureka.client.fetch-registry=false
eureka.server.enableSelfPreservation=true
eureka.server.renewalPercentThreshold=0.85

# Server Port
server.port=8761
```

Make sure to update the configuration according to your requirements, such as the server port.

## Deployment
The Eureka Server can be deployed as a standalone Spring Boot application. It should be the first service started in the microservices architecture.

## Endpoints
The Eureka Server exposes the following endpoints:

- `GET /eureka/apps`: Retrieves a list of all registered services.
- `GET /eureka/apps/{serviceId}`: Retrieves the details of a specific registered service.

## Dependencies
- Spring Boot
- Spring Cloud Netflix Eureka Server

## Known Issues
- The Eureka Server does not have any authentication or authorization mechanisms in place.
- The error handling and logging could be improved.

## Future Improvements
- Implement authentication and authorization for the Eureka Server.
- Improve the error handling and logging mechanisms.
- Add more test cases to ensure the reliability of the service registry.