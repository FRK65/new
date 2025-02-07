

**Q:1** What is the difference between `@Autowired` and `@Qualifier` in Spring Boot?

🔹 **`@Autowired` – Automatic Dependency Injection**
- Automatically injects beans into Spring components.
- Can be used with constructor injection, setter injection, or field injection.
- If multiple beans of the same type exist, it throws an ambiguity error unless resolved.

**Example:**

```java
@Service
public class PaymentService {
 
    @Autowired
    private PaymentProcessor paymentProcessor; // Automatically injected
}
```
✔ Spring automatically injects the `PaymentProcessor` bean.

---

🔹 **`@Qualifier` – Resolves Bean Ambiguity**
- Used when multiple beans of the same type exist.
- Specifies which bean should be injected.
- Works together with `@Autowired`.

**Example (Multiple Beans Issue):**

```java
@Component
public class PayPalProcessor implements PaymentProcessor { }

@Component
public class StripeProcessor implements PaymentProcessor { }

@Service
public class PaymentService {
 
    @Autowired
    @Qualifier("stripeProcessor") // Specifies which bean to inject
    private PaymentProcessor paymentProcessor;
}
```
✔ Without `@Qualifier`, Spring will fail due to multiple `PaymentProcessor` beans.

---

### 🔍 **Key Differences Between `@Autowired` and `@Qualifier`:**

| **Feature**               | **`@Autowired`**                              | **`@Qualifier`**                            |
|---------------------------|-----------------------------------------------|--------------------------------------------|
| **Purpose**               | Automatically injects a bean                  | Specifies which bean to inject            |
| **Handles Multiple Beans?** | No, causes an error                          | Yes, resolves ambiguity                   |
| **Requires Bean Name?**    | No                                            | Yes, requires a bean name                 |
| **Used With?**             | Constructor, setter, or field injection       | Always used with `@Autowired`             |

---

### 🔥 **Follow-Up Questions:**

**Q:2**  Can we use `@Autowired` without `@Qualifier` when multiple beans exist?  
No, you cannot use @Autowired without @Qualifier (or some other mechanism) when multiple beans of the same type exist.

When you have multiple beans of the same type in the Spring context, Spring will throw an 
**org.springframework.beans.factory.NoUniqueBeanDefinitionException**, 
because it won't know which bean to inject. To resolve this ambiguity, you need to tell Spring which bean to inject.

**Q:2** How do we handle multiple beans if we don’t want to use `@Qualifier`?  
If you don’t want to use **@Qualifier** to handle multiple beans of the same type, you can consider the following approaches:
1.**The @Primary annotation** can be used to mark one of the beans as the default bean to be injected when there is ambiguity. 
If a bean is annotated with @Primary, 
Spring will choose that bean automatically when there are multiple beans of the same type, unless otherwise specified.

2. **Use @Bean Method with Explicit Configuration** - You can also configure beans explicitly in your configuration class using @Bean methods.
   This way, you can control which beans are instantiated and injected without relying on @Qualifier.

3. Use Custom Annotations
   If @Qualifier is not an option, you can create your own custom annotations to mark and differentiate beans. You could use these annotations in conjunction with @Autowired to resolve the ambiguity.


**Q:3**  What is the difference between `@Primary` and `@Qualifier`?

`@Primary` : Marks a bean as the default when multiple beans exist.
`@Qualifier`: Specifies exactly which bean to inject.

`@Primary` : Automatically applied when there is ambiguity.
`@Qualifier`: Must be explicitly used when needed.

Use **@Primary** when you have a default bean that should be injected unless otherwise specified.
Use **@Qualifier** when you need to resolve ambiguity and specify exactly which bean to inject in a particular case



