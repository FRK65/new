**JUnit** and **Mockito** 

### JUnit Interview Questions:

1. **What is JUnit?**
- JUnit is a widely used testing framework for Java programming.
- It is used for unit testing Java applications.
- It helps in automating the testing of the code by providing **annotations**, **assertions**, and test runners to simplify testing.

2. **What are JUnit annotations?**
Some of the commonly used JUnit annotations are:
     - `@Test`: Marks a method as a test method. eg. testInvalidPassword();
     - `@Before`: Executes before each test method. eg. if class have 5 test methods then it will execute 5 times before each testcase.
     - `@After`: Executes after each test method. eg. if class have 5 test methods then it will execute 5 times after each testcase.
     - `@BeforeClass`: Executes once before all test methods in a class. eg. it will execute Before starting execution of testcases.
     - `@AfterClass`: Executes once after all test methods in a class. eg. it will execute After Finishing execution of testcases.
     - `@Ignore`: Ignores a test method.
     - `@Test(expected = Exception.class)`: Specifies that the test should throw a specific exception.

3. **What is the difference between `@Before` and `@BeforeClass`?**
   
     - `@Before`: Runs before each test method (i.e., it is executed before every individual test method).
     - `@BeforeClass`: Runs only once before any test methods in the class.
       It is static, so it can be used to set up resources, such as database connections.

4. **What is a Test Case in JUnit?**
   - A Test Case is a method annotated with `@Test` in JUnit.
   - It defines a unit of testing. It verifies whether the code works as expected by asserting the expected results against actual results.

5. **What are assertions in JUnit?**

   Assertions are used to validate expected results in test cases. Some commonly used assertions are:
     - **`assertEquals(expected, actual)`**: Verifies if expected and actual values are the same.
     - **`assertTrue(condition)`**: Verifies if the condition is true.
     - **`assertFalse(condition)`**: Verifies if the condition is false.
     - **`assertNull(object)`**: Verifies if the object is null.
     - **`assertNotNull(object)`**: Verifies if the object is not null.

7. **What is the use of `@After` annotation?**
   - The `@After` annotation is used to execute any cleanup code after each test method. It is typically used for closing resources like file streams or database connections.
