
# 1. What is Lambda expression.

**Lambda is an anonymous function.**
A Lambda expression is a feature in programming languages that allows us to 
create anonymous functions (functions that do not have a name). 
These functions are typically used to write **concise, short code**, especially 
when you need to **pass behavior as an argument to methods or functions**.

for batter understanding, write a simple function that return sum of two number.
```java
int sum(int a, int b) {

    return a+b;
}
```

Lambda is an anonymous function. means
1. No function name.
2. No Modifier.
3. No return type.

Now, Write the same function again by follow above steps.
```java
  ( int a, int b) { return a + b; }
```
More consice way is 
```java
  (a,b) -> a + b;
```

**For Eg. WAP for sum of two number**
```java
@FunctionalInterface
interface Sum_interface {
    int add(int a, int b);
}

public class SumUsingLambda {
    public static void main(String[] args) {
        
        Sum_interface sum = (a, b) -> a + b;

        int result = sum.add(5, 3);
        System.out.println("The sum is: " + result);
    }
}
```
The line F_Sum sum = (x, y) -> (x + y); 
- creates a lambda expression that implements the add() method of the F_Sum interface,
- allowing the sum variable to hold the logic for adding two integers.
- It creates a variable **sum** of type **Sum_interface** (which is the functional interface you defined).
- It assigns to sum the lambda expression (x, y) -> (x + y)
  that defines the implementation of the add method.
  Now, sum is an instance of Sum_interface, but it uses the lambda expression to define how the add method works.



**For Eg. WAP for sum of two number using BiFunction<Integer, Integer, Integer> function_name**

**BiFunction<T, U, R> function_name;**
1. T (First Type Argument)
2. U (Second Type Argument)
3. R (return Type )

```java
import java.util.function.BiFunction;
public class Sum {

     public static void main(String []args) {
        
        BiFunction<Integer,Integer,Integer> fun = (x,y)->(x+y);
        int res = fun.apply(3,4);
        System.out.println(res);
        
     }
}
```


