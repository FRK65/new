# @Transactional annotation

The @Transactional annotation in Spring Boot is a powerful feature that helps manage 
database transactions with ease. 
When applied to a method or class, it ensures that all operations within the 
method are executed as part of a single transaction.

If any exception occurs, the transaction is automatically rolled back, 
maintaining data consistency and preventing partial updates. 
This is especially useful in scenarios like creating orders, updating inventories, or handling payments.

In short, @Transactional simplifies transaction management, saving you from writing
boilerplate code and reducing the risk of data inconsistencies
