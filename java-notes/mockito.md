### Mockito Interview Questions:

1. **What is Mockito?**
   - Mockito is a popular mocking framework for unit testing in Java.
   - It allows you to mock objects,
   - so you can isolate the behavior of the class being tested and avoid external dependencies (e.g., databases, network services).

2. **What is a mock object?**
   - A mock object is a simulated object that mimics(duplicate) the behavior of real objects in a controlled way.
   - It is used in unit tests to isolate the component being tested from its dependencies.

3. **What is the difference between `@Mock` and `Mockito.mock()`?**
   
     - **`@Mock`**: It is an annotation used to create mock objects automatically. You need to use **`MockitoAnnotations.initMocks()`** to initialize them.
     - **`Mockito.mock()`**: It is a static method to create a mock object manually by passing the class type as an argument.

4. **How can you verify the interactions with a mock object?**
   - Mockito allows you to verify interactions with mock objects using the `verify()` method. For example:
     ```java
     verify(mockObject).methodName(); // Verifies if the method was called at least once
     verify(mockObject, times(1)).methodName(); // Verifies if the method was called exactly once
     ```

5. **What is `when` and `thenReturn` in Mockito?**
  
     - **`when`**: It is used to define the behavior of a mock object. For example, **`when(mock.method()).thenReturn(value)`** defines that when the** `method()`** is called, it should return the specified **`value`.**
     - **`thenReturn`**: It is used to specify the return value for a mocked method.

6. **What is the purpose of `@InjectMocks`?**
   - The **`@InjectMocks**` annotation is used to automatically inject mock objects into the object being tested.
   - It helps in creating an instance of the class under test and injects all the `@Mock` fields into it.

7. **What is a spy in Mockito?**
   -  spy is a partial mock. Unlike a mock object, which provides a fully mocked version of a class, a spy allows you to mock only specific methods of a real object, while leaving others to behave as normal. For example:
     ```java
     List<String> spyList = spy(new ArrayList<>());
     spyList.add("hello");
     verify(spyList).add("hello");
     ```

8. **What is the difference between `mock()` and `spy()` in Mockito?**
   - **Answer**: 
     - `mock()`: Creates a completely mocked object, where all methods are stubbed with default values (e.g., `null`, `0`, `false`).
     - `spy()`: Creates a real object and allows you to mock only specific methods, keeping the behavior of the other methods intact.

9. **What does `doThrow()` do in Mockito?**
   - **Answer**: `doThrow()` is used to stub void methods that throw exceptions. For example:
     ```java
     doThrow(new RuntimeException()).when(mockObject).voidMethod();
     ```

10. **How do you mock a static method with Mockito?**
    - **Answer**: You need to use `Mockito.mockStatic()` (available in Mockito 3.4+) to mock static methods. For example:
      ```java
      try (MockedStatic<MyClass> mockedStatic = Mockito.mockStatic(MyClass.class)) {
          mockedStatic.when(() -> MyClass.staticMethod()).thenReturn("mocked result");
      }
      ```
