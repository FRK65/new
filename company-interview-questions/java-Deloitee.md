
# Deloitee 

Answer all this interview questions as i have to answered in mock interview use real life exaple to explain as i have to speak and tell this interviewer. 
1. Communication between microservices
2. What is encapsulation
3. Differences between abstract class and interface
4. What is exception handler
5. If ur controller receives multiple requests at time by client how would you handle those
6. What is circuit design pattern
7. What are solid design principles
8. What is default methods, can you override it
9. What is singleton design pattern explain with example
10. Guess the program output on static blocks
11. Profiling in springboot
12. Guess the program output on strings equals and == operator example
13. Differences between put and patch
14. Differences between final ,finally, finalize
15. differences between @requestparam and @path variable give example
16. How db configured and integrated with springboot
17. what is dispatcher servlet and service registry, how the Eureka server used as centralized node
18. Executor framework
19. lifecycle of thread
20. can you run thread by using run method without start() method if not why
21. how to test mockito test cases and annotation used
22. in jpa if ur using inbuilt queries like findbyid if no record found for that , what will be output ,any exception thrown?
23. explain the flow of layers ur using and explain how u created APIs from controller to repository.
24. given list of integers and asked to sort the elements based on ascending order.
25. Types of exceptions with examples.
26. What is spring actuator how do you incorporated in ur project 


Sure! I’ll answer these interview questions using real-life examples to help you explain them effectively during a mock interview.

### 1. **Communication between Microservices**
Microservices often communicate using **REST APIs**, **gRPC**, or **message brokers** (like RabbitMQ, Kafka). 
For example, in a shopping cart microservice system, the **cart service** could communicate with the **product service** to check if an item is in stock using a RESTful API call. 
If there’s a need for asynchronous communication (e.g., notifying users about a shipment), the services can exchange messages via Kafka.

### 2. **What is Encapsulation?**
Encapsulation is a concept where data (variables) and methods that operate on the data are bundled together. 
It hides the internal state and requires all interactions to be performed through well-defined interfaces (methods).  

**Real-life example**: Think of a **car**. You can drive it (interact with it), but you don't need to know how the engine works under the hood. The car's engine, fuel tank, and wheels are the internal state, while the **steering wheel** and **accelerator** are the exposed methods to interact with the car.

### 3. **Differences Between Abstract Class and Interface**
- **Abstract Class**: Can have both abstract (no body) and concrete methods (with body). It can hold state (instance variables).
- **Interface**: Only defines method signatures, and the implementing class must provide the method bodies.  
  **Real-life Example**: An **abstract class** is like a blueprint for a **vehicle** that has general methods like `start()` (but no specific implementation). An **interface** is like a contract that says any vehicle must have methods like `accelerate()` and `brake()` but doesn't define how those actions are performed.

  **NOTE**: Abstract class is used when no multiple inheritance is required means it has limitation of extending only one class,
	while interface is used when multiple inheritance is required.

### 4. **What is Exception Handler?**
An exception handler is used to handle exceptions in a way that doesn't crash the program. It catches specific exceptions and responds accordingly.  
**Example**: In a Spring Boot application, you might use `@ControllerAdvice` to handle exceptions globally. For instance, if a user submits invalid data, you can return a specific error message instead of letting the app crash.

### 5. **If your controller receives multiple requests at a time from a client, how would you handle those?**
Spring Boot handles concurrent requests (multiple requests) by utilizing thread pools, where each request is processed in its own thread. 

You could also use **Asynchronous Processing** (via `@Async` or `CompletableFuture`) for better performance when processing time-consuming tasks like sending emails or fetching data from an external API.

### 6. **What is Circuit Design Pattern?**
The **Circuit Breaker** pattern is used to detect failures and prevent the system from repeatedly performing operations that are likely to fail. 
It “breaks the circuit” and redirects to a fallback method.  

**Real-life example**: In an e-commerce application, if a payment gateway service fails repeatedly, 
the circuit breaker pattern prevents further requests to it and instead returns a **"service unavailable"** message.

### 7. **What Are SOLID Design Principles?**
- **S**: Single Responsibility Principle (SRP)
- **O**: Open/Closed Principle
- **L**: Liskov Substitution Principle
- **I**: Interface Segregation Principle
- **D**: Dependency Inversion Principle  


### 8. **What is Default Methods, Can You Override It?**
Default methods are, methods in interfaces that have a body. 
They allow backward compatibility in Java 8+ interfaces. Yes, you can override a default method in the implementing class if needed.  
**Example**: In an interface `Animal`, you might have a default method `sound()`, which can be overridden by specific classes like `Dog` or `Cat` to provide their own sound.

### 9. **What is Singleton Design Pattern, Explain With Example**
The **Singleton Design Pattern** ensures a class has only one instance and provides a global point of access to it.  
**Example**: A **configuration manager** class in your application that loads settings once and ensures all other 
components use the same instance, like logging settings or database connection settings.

### 10. **Guess the Program Output on Static Blocks**
Static blocks are executed when the class is loaded into memory. For example, in the following:
   ```java
   class Test {
       static {
           System.out.println("Static Block");
       }
   }
   ```
The output will be `"Static Block"` when the class is loaded. This happens before the main method runs.

### 11. **Profiling in Spring Boot**
Profiling is used to identify performance bottlenecks. 
Spring Boot provides tools like **Spring Boot Actuator** for production diagnostics and performance monitoring.  
**Example**: You could use **`@Profile`** to define beans that are activated under certain environments (e.g., dev, prod). 
You might also use the **Actuator’s `/actuator/metrics`** endpoint to get real-time performance data.

### 12. **Guess the Program Output on String’s `equals` and `==` Operator Example**
The **`equals()`** method compares the content of strings, while **`==`** compares their references.
   ```java
   String str1 = new String("test");
   String str2 = new String("test");
   System.out.println(str1 == str2);  // false
   System.out.println(str1.equals(str2));  // true
   ```

### 13. **Differences Between PUT and PATCH**
- **PUT**: Replaces the entire resource or creates a new one if not found.
- **PATCH**: Updates only the fields that are provided in the request.  
  **Example**: In a user profile update, if you change the user’s name, a `PATCH` request would only update the name, while a `PUT` request would replace the entire user object.

### 14. **Differences Between Final, Finally, Finalize**
- **`final`**: Used for constants, methods that cannot be overridden, and classes that cannot be extended.
- **`finally`**: Block that runs after `try-catch`, used for cleanup.
- **`finalize`**: Method in `Object` class called by the garbage collector before an object is destroyed.  
  **Example**:
   ```java
   final int MAX = 100;  // constant  
   try {
       // some code
   } finally {
       // cleanup code
   }
   ```

### 15. **Differences Between `@RequestParam` and `@PathVariable`, Give Example**
- **`@RequestParam`**: Retrieves query parameters from the URL.
- **`@PathVariable`**: Retrieves values from the URI path.  
  **Example**:
   ```java
   @GetMapping("/users/{id}")
   public User getUser(@PathVariable String id) { return userService.getById(id); }
   
   @GetMapping("/users")
   public User getUser(@RequestParam String id) { return userService.getById(id); }
   ```

### 16. **How is DB Configured and Integrated with Spring Boot?**
In Spring Boot, DB integration is typically done via **JPA** or **JDBC**:
- Define datasource properties in `application.properties` or `application.yml`.
- Use **Spring Data JPA** repositories or **JdbcTemplate** to interact with the database.  
  **Example**:
   ```properties
   spring.datasource.url=jdbc:mysql://localhost:3306/mydb
   spring.datasource.username=root
   spring.datasource.password=root
   spring.jpa.hibernate.ddl-auto=update
   ```

### 17. **What is Dispatcher Servlet and Service Registry, How Eureka Server Used as Centralized Node**
- **Dispatcher Servlet**: It is the front controller in Spring MVC that routes requests to appropriate handlers.
- **Eureka Server**: A service registry where services register themselves for discovery.  
  **Example**: In a microservices architecture, a service like `user-service` registers with Eureka, and other services like `order-service` can discover `user-service` dynamically.

### 18. **Executor Framework**
The **Executor Framework** provides a higher-level replacement for the traditional way of managing threads. It abstracts thread creation and management.  
**Example**: Using `ExecutorService` to manage a pool of threads for handling multiple user requests concurrently.

### 19. **Lifecycle of a Thread**
A thread can be in one of these states:
- **New**: When a thread is created but not yet started.
- **Runnable**: When the thread is ready to run but may not be currently running.
- **Blocked**: When a thread is waiting for a resource.
- **Terminated**: When the thread finishes its execution.

### 20. **Can You Run a Thread by Using `run()` Method Without `start()`?**
No, calling `run()` directly will not start a new thread. It will just execute the `run()` method in the current thread. You need to call `start()` to initiate a new thread.

### 21. **How to Test Mockito Test Cases and Annotations Used**  
In Mockito, you use annotations like `@Mock`, `@InjectMocks`, and `@Before`.  
**Example**:
   ```java
   @Mock
   private MyService myService;
   
   @InjectMocks
   private MyController myController;
   ```

### 22. **In JPA, If You're Using Inbuilt Queries Like `findById` and No Record is Found, What Will Be the Output? Any Exception Thrown?**
If `findById()` doesn't find a record, it returns `Optional.empty()`. It does **not** throw an exception. You can handle it by checking `Optional.isPresent()`.

### 23. **Explain the Flow of Layers You’re Using and Explain How You Created APIs from Controller to Repository**
In a typical layered architecture:
- **Controller**: Receives the HTTP request and delegates to service.
- **Service**: Contains business logic and calls repository.
- **Repository**: Interacts with the database (via JPA or JDBC).  
  Example: For a `User` entity, you create a `UserController` that calls `UserService`, which in turn calls `UserRepository` for DB operations.

### 24. **Given List of Integers and Asked to Sort the Elements Based on Ascending Order**
Use the `Collections.sort()` method or the `Stream` API.
   ```java
   List<Integer> numbers = Arrays.asList(3, 1, 4, 1, 5, 9);
   Collections.sort(numbers);
   ```

### 25. **Types of Exceptions with Examples**
- **Checked Exception**: Exception that must be handled (e.g., `IOException`).
- **Unchecked Exception**: Exception that can occur during runtime (e.g., `NullPointerException`).

### 26. **What is Spring Actuator, How Do You Incorporate It in Your Project?**
Spring Actuator provides production-ready features like metrics, health checks, and monitoring.  
To incorporate it, add the dependency to your `pom.xml` and enable endpoints like `/actuator/health`.  
**Example**:
   ```xml
   <dependency>
       <groupId>org.springframework.boot</groupId>
       <artifactId>spring-boot-starter-actuator</artifactId>
   </dependency>
   ```
