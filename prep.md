What happens when an order is placed?
When a user places an order, the frontend sends a request to the ASP.NET Core Web API.
The API validates the request, saves the order and order items in the database using a transaction, and then publishes an event message to Azure Service Bus.
This message is later consumed by an Azure Function which sends email and SMS notifications asynchronously.

Why use Azure Service Bus instead of sending email directly?
Sending email directly inside the API would block the request and slow down the user experience.
Azure Service Bus allows us to decouple order processing from notification processing.
Even if the notification service is slow or temporarily unavailable, the order placement still succeeds, ensuring reliability and scalability.

What is asynchronous processing?
Asynchronous processing means executing time-consuming tasks in the background without blocking the main application flow.
In this system, order placement is handled synchronously, while notifications are processed asynchronously using a queue and background worker.

Why are roles needed?
Roles are used to control access to different functionalities.
Customers can place and view their own orders, while admins can manage all orders and view system-level reports.
Role-based authorization improves security and follows the principle of least privilege.
