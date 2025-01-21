# Building-a-Retail-Inventory-Management-System

This project involves developing an inventory management system for an e-commerce company called ShopSmart using Object-Oriented Programming (OOP) in Python. The goal is to manage the company's inventory efficiently and enable the placement of orders by customers. The system consists of two main classes: Product and Order. Below is a description of the project and the steps taken in designing the classes and their methods:

1. Class Design and Functionality:
Product Class:
Purpose: This class represents a product in the inventory, and it includes attributes such as product ID, name, category, quantity, price, and supplier. It also manages the inventory of products.

Constructor (__init__): Initializes a product object with the necessary details (e.g., product ID, name, category, etc.) and appends the instance to the class-level list inventory.

Class-level variable inventory: This list stores all the products in the inventory. It is shared among all instances of the class.

Methods:

add_product(cls, name, category, quantity, price, supplier): This class method adds a new product to the inventory. It generates a unique product_id for each product by incrementing the ID of the last product in the inventory. After creating a new product instance, it returns a success message.

update_product(cls, product_id, quantity=None, price=None, supplier=None): This method allows for updating a product's details. If a product with the provided product_id is found, its attributes (quantity, price, supplier) are updated based on the provided values. It returns a success message if the update is successful or an error message if the product is not found.

delete_product(cls, product_id): This method deletes a product from the inventory. It searches for the product using the product_id and removes it if found, returning a confirmation or error message.

Order Class:
Purpose: This class represents an order placed by a customer. It contains the order ID, the products ordered (as a list of tuples containing product IDs and quantities), and optional customer information.

Constructor (__init__): Initializes an order object with an order ID, a list of products (initially empty), and optional customer information.

Method:

place_order(self, product_id, quantity, customer_info=None): This method is responsible for placing an order. It checks if the product exists in the inventory and if there is sufficient stock. If so, it reduces the stock and adds the product (with quantity) to the order's product list. The customer information is also updated if provided. The method returns a success message with the order ID or an error message if the product is unavailable or there is insufficient stock.
2. Key Steps Taken in the Implementation:
Step 1: Design Product Class and Methods
Defined the attributes for the Product class, including the product ID, name, category, quantity, price, and supplier.
Implemented methods to add, update, and delete products.
Ensured that the product_id is auto-generated and unique by checking the last product ID in the inventory.
Step 2: Design Order Class and Methods
Defined the attributes for the Order class, including the order ID, products, and optional customer information.
Implemented the place_order method to check product availability, update stock, and add products to the order. If the order is successfully placed, the method updates the order details and returns a confirmation message.
Step 3: Handle Inventory and Orders
The Product class manages the overall inventory, storing all products in a shared class-level variable.
The Order class allows customers to place orders by selecting a product from the inventory and specifying the desired quantity. It checks if the product is available and ensures that the stock is updated after each order placement.
3. Example Usage:
Adding a Product:

A product can be added using the add_product method. For example, you can add a laptop to the inventory:
python
Kopiera
Redigera
p1 = Product.add_product("Laptop", "Electronics", 50, 1000, "Supplier A")
Updating a Product:

If the quantity or price of a product needs to be updated, you can use the update_product method:
python
Kopiera
Redigera
update_p1 = Product.update_product(1, quantity=45, price=950)
Deleting a Product:

To remove a product from the inventory, the delete_product method is used:
python
Kopiera
Redigera
delete_p1 = Product.delete_product(1)
Placing an Order:

A customer can place an order for a product with a specific quantity:
python
Kopiera
Redigera
order = Order(order_id=1, products=[])
order_placement = order.place_order(1, 2, customer_info="John Doe")
4. Conclusion:
The project demonstrates how to build a functional inventory management system using OOP principles in Python. The Product class manages the inventory, while the Order class handles customer orders. This structure ensures that the code is modular, reusable, and maintainable, which is essential for managing a growing e-commerce business like ShopSmart. The system can easily be expanded to support additional features such as multiple product orders, more detailed customer information, and advanced stock management.







