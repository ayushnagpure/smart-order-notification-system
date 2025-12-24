## System Architecture

The application follows a layered architecture:

- React frontend communicates with ASP.NET Core Web API using REST APIs
- Backend API handles authentication, order processing, and data persistence
- Azure Service Bus is used for asynchronous notification messaging
- Azure Functions consume messages and send email/SMS notifications
- SQL Server stores transactional data
- Application Insights is used for monitoring and logging


## Modules

1. Authentication Module
2. Order Management Module
3. Notification Module
4. Admin Reporting Module
