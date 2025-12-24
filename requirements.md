User Management:
Users can log in using email & password
JWT-based authentication
Roles:
  Admin
  Customer

Order Management:
Customer can:
  Place an order
  View order history
  Track order status
Admin can:
  View all orders
  Update order status

Order lifecycle:
Placed → Confirmed → Shipped → Delivered

Notification System (ASYNC):
When an order is placed:
  Email notification is sent
  SMS notification is sent
Notifications are processed asynchronously using a queue
Failed notifications go to Dead Letter Queue (DLQ)

Admin Dashboard:
View total orders
Orders by status
Recent notifications


Non-Functional Requirements:
(Add this section in the same file)
Secure APIs using JWT authentication
Scalable architecture using async messaging
Centralized logging and monitoring
Separation of concerns (Clean Architecture)
Cloud deployment using Azure
