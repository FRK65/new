# SOLID Principles

The **SOLID** principles are a set of five design principles 
in object-oriented programming (OOP) that helps developers to create more 
**maintainable**, **flexible**, and **scalable software**. 
They were introduced **by Robert C. Martin**, also known as Uncle Bob. 


### 1. **S: Single Responsibility Principle (SRP)**
   - **Definition**: A class should have only one reason to change, meaning it should have only
     one job or responsibility.
  
### 2. **O: Open/Closed Principle (OCP)**
   - **Definition**: Software entities (classes, modules, functions, etc.) should be open for
     extension but closed for modification. This means you can add new functionality without
     changing existing code.

### 3. **L: Liskov Substitution Principle (LSP)**
   - **Definition** : Objects of a superclass should be replaceable with objects of its
     subclasses without affecting the correctness of the program.
   - **simple** : If you have a class and a subclass, you should be able to replace the
     parent class with the child class without breaking anything in the program
  
### 4. **I: Interface Segregation Principle (ISP)**
   - **Definition**: Clients should not be forced to depend on interfaces they do not use.
     This principle advocates for creating smaller, more specific interfaces instead of a
     large, monolithic one.
  - **simpel**: do not force any client to implement an interface which is irrelevant to them

### 5. **D: Dependency Inversion Principle (DIP)**
   - **Definition**: High-level modules should not depend on low-level modules.
     Both should depend on abstractions (e.g., interfaces or abstract classes).
     Furthermore, abstractions should not depend on details; details should depend on abstractions.

# REAL Life Example of all 

# 1. **S: Single Responsibility Principle (SRP)**

Imagine a cook who is responsible for cooking Food.
The cooke’s role is to focus on the task of cooking Food Only,
ensuring that the Food is of high quality, properly cooked, and meets the Restaurant’s standards.
Not the inventory, ordering supplies, serving customers, and cleaning, this would violate the SRP.
```java

class Cook {
    public void cookingFood() {
        System.out.println("Cook high-quality Food...");
    }
}

class InventoryManager {
    public void manageInventory() {
        System.out.println("Managing inventory...");
    }
}

class CustomerService {
    public void serveCustomer() {
        System.out.println("Serving customers...");
    }
}

class RestaurantCleaner {
    public void cleanBakery() {
        System.out.println("Cleaning the bakery...");
    }
}

public class Restaurant {
    public static void main(String[] args) {
        
        Cook cook = new Cook();
        InventoryManager inventoryManager = new InventoryManager();
        CustomerService customerService = new CustomerService();
        RestaurantCleaner cleaner = new RestaurantCleaner();

        cook.cookingFood();
        inventoryManager.manageInventory();
        customerService.serveCustomer();
        cleaner.cleanBakery();
    }
}

```

# 2. **O: Open/Closed Principle (OCP)**

**Scenario**: When you order food, you can apply different types of coupons, and each coupon has a
specific discount logic.
The goal is to extend the system to accommodate new coupon types without changing
the core functionality of the system.

**Approach**:
- **Coupon types**: You’ll have different coupon types, such as **FlatDiscount**, **TryNewUserDiscount**,
  **OrderAboveAmountDiscount**, and **PaymentMethodDiscount**.

- **ShoppingCart**: It will apply the coupon logic based on the user's choice of coupon,
  without changing the structure when new coupons are added.

  ```java
  //The Coupon interface
  
  public interface Coupon {
      double applyCoupon(double totalAmount);
  }
  ```
  
  ```java
  public class FlatDiscountCoupon implements Coupon {
    private double discountAmount;

    public FlatDiscountCoupon(double discountAmount) {
        this.discountAmount = discountAmount;
    }

    @Override
    public double applyCoupon(double totalAmount) {
        return totalAmount - discountAmount;
    }
  }
  ```
  ```java
  public class PaymentMethodDiscount implements Coupon {
    private String paymentMethod;
    private double discountPercentage;

    public PaymentMethodDiscount(String paymentMethod, double discountPercentage) {
        this.paymentMethod = paymentMethod;
        this.discountPercentage = discountPercentage;
    }

    @Override
    public double applyCoupon(double totalAmount) {
        // Assuming user chooses Paytm for payment
        if (paymentMethod.equals("Paytm")) {
            return totalAmount - (totalAmount * discountPercentage);
        }
        return totalAmount;
    }
   }
  ``` 
 
# 3. **L: Liskov Substitution Principle (LSP)**

**Payment Methods in an E-Commerce App:**

Imagine you’re using an online shopping app like Amazon, Flipkart. When you check out your cart and
proceed to payment, you can choose different payment methods:
Credit Card, Debit Card, UPI, Cash on Delivery (COD),

All of these payment methods inherit from a common base concept of class "PaymentMethod,"
and they should be substitutable in the same system.

**Without Liskov’s Substitution Principle (Wrong Approach):**
If you don’t follow LSP, you might create different types of payment methods,
but each payment type could end up having a lot of inconsistent behaviors.
Eg. the app has a common PaymentMethod class, and then each specific payment method overrides a
processPayment() method differently, which can introduce unexpected results.

**With Liskov’s Substitution Principle (Right Approach):**
we need to make sure that every payment method behaves in a way that’s consistent with the rest of 
the payment methods and doesn’t introduce unexpected behaviors. 
The processPayment() method in all payment types should behave in a standardized way. 
Even though each payment type might have its own implementation details, 
they should all process payments in a predictable way



