# DispatcherServlet

# Dispatcher Servlet
Servlet is a Core Standard Browser APIs that processes HTTP request and return the response whereas a DispatcherServlet is a specific and advanced implementation used in the Spring MVC and Spring Boot Framework.



## Why do we need it?
Without a Dispatcher Servlet, we have to manually map every URL to a specific servlet which becomes unmanageable.

Reasons for using a DispatcherServlet are:-

**1.Centralized Request Handling**:-It receives all the incoming HTTP request from a single entry point and decide which controller should process it, by preventing code duplication.

**2.Automated Routing(Handler Mapping)**:-It uses Handler Mapping to find controller and method to handle a specific URI.

**3.View Resolution**:-A Dispatcher cannot render logical view name so it uses view resolution to translate logicalview name to physical file, like JSP or HTML page.

**4.Integrated with Spring Features**:-The DispatcherServlet is fully aware of the Spring Context, it give our web layer a direct access to major spring features.

## Working
**DispatcherServlet**:-HTTP Request received by DispatcherServlet.

**Handler Mapping**:-Decide which controller should handle the request.

**Controller**:-The controller process the request and return logical view name.

**View Resolution**:-translate the logical view name to physical file like JSP or HTML page.

**View**:-View the rendered file.

**Response**:-Rendered view is send back to the client as a HTTP response.

![App Screenshot](https://media.geeksforgeeks.org/wp-content/uploads/20260228113317618539/spring_mvc_architecture.webp)

## Benefits
**Front Controller Pattern**:- It provide single entry point for request by eliminating the need to create individual entry point for each request.

**Loose Coupling**:- Controller, View Resolver, and Exception handler are completely decoupled.

**Automatic Request Routing**:-It automatically analyze the request and map them to the correct controller.

**Seamless view and Data Resolution**:-It coordinate with View Resolver and automatically render the response.

**Centralized Exception Handling**:- Here we can handle the global exception in one place.
## Drawbacks of DispatcherServlet
**Tight Coupling with Spring Framework**:-If we want to switch to different web framework we need to rewrite the entire request-handling architecture.

**Single Point Failure**:-As it consist of single entry point for all the request, any misconfiguration can lead the DispatcherServlet to crash or slow down the entire application.

**Complexity**:-Understanding the interaction of DispatcherServlet with secondary component is not easy.

**Configuration overhead**:-Manually configuring the DispatcherServlet, initializing parameters and URL mapping can be error-prone.

**Increased Startup Time**:- It takes Considerable time to initialize its internal WebApplicationContext which increase application startup time.

**Overhead for Simple APIs**:-For simple microservices and REST APIs, the Spring MVC by DispatcherServlet is considered heavyweight.

**NOTE**:-The Drawbacks of DispatcherServlet like, Tight Coupling, Overhead for Simple APIs, Heavy Resource Consumption gave emergence to ***Spring WebFlux*** and ***Microframeworks***.
