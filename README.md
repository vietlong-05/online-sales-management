# online-sales-management
src/models/product.py
class Product:
    def __init__(self, product_id, name, description, price, stock):
        self.product_id = product_id
        self.name = name
        self.description = description
        self.price = price
        self.stock = stock

    def update_stock(self, quantity):
        self.stock += quantity

    def __str__(self):
        return f"{self.name} - {self.price} VND"
src/models/customer.py
class Customer:
    def __init__(self, customer_id, name, email, phone, address):
        self.customer_id = customer_id
        self.name = name
        self.email = email
        self.phone = phone
        self.address = address

    def __str__(self):
        return f"Customer: {self.name} - {self.email}"
src/models/order.py
class Order:
    def __init__(self, order_id, customer, items):
        self.order_id = order_id
        self.customer = customer
        self.items = items  # List of tuples: (Product, quantity)
        self.status = "Pending"
src/models/order.py
    def total_price(self):
        return sum(product.price * quantity for product, quantity in self.items)

    def update_status(self, new_status):
        self.status = new_status
