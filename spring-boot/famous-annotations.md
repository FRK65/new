
# 1. What is the purpose of the @RestController annotation?
The **@RestController** annotation is used in Spring Boot to indicate that a class is a
special version of the **@Controller** annotation. 
It specifically used for building RESTful web services. 

It combines the @Controller and @ResponseBody.
**@RestController = @Controller + @ResponseBody.**

When you annotate a class with @RestController, then @RestController add the 
@ResponseBody to each handler method of that class implicitly.
And Spring Boot treats all the handler methods of that class as being responsible for generating the
response body for RESTful requests. 
It eliminates the need to annotate individual methods with @ResponseBody because @RestController implicitly adds it
to all the methods.
 
The @RestController annotation simplifies the development of RESTful web
services by eliminating the need to explicitly annotate every method with
@ResponseBody and makes it more concise and expressive.

# 2. 
