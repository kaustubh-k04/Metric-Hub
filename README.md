# Metric-Hub
MetricHub is a backend-focused system design project built using Spring Boot that demonstrates clean layered architecture, RESTful APIs, and modular service design.

Overview

MetricHub is designed as a layered backend system where each component has a clearly defined responsibility.
The goal of this project is to understand how real-world backend systems are structured, rather than focusing only on feature implementation.

🏗️ System Architecture Explanation

The system follows a standard enterprise backend architecture consisting of the following layers:

1️⃣ Clients Layer

This is the entry point of the system.

Includes Web Applications and external API integrations

Sends HTTP requests for submitting or retrieving user and metric data

Communicates with the backend using REST APIs

Purpose:
To act as the consumer of backend services.

2️⃣ API Layer (Spring Boot – REST APIs)

This layer handles all incoming HTTP requests.

Components:

MetricController

UserController

Responsibilities:

Accept HTTP requests from clients

Perform basic input validation

Forward requests to the appropriate service layer

Return responses back to the client

Why this layer exists:
It separates request handling from business logic, improving readability and maintainability.

3️⃣ Service Layer (Business Logic – Java)

This is the core logic layer of MetricHub.

Components:

MetricService

UserService

Responsibilities:

Process business rules

Handle metric tracking and user operations

Coordinate between controllers and the data layer

Manage error handling logic

Design Focus:
Clean architecture, modular services, and scalability.

4️⃣ Repository Layer (Spring Data)

This layer abstracts all database operations.

Responsibilities:

Perform CRUD operations

Interact with the database using Spring Data

Keep database logic separate from business logic

Benefit:
Makes the system easier to test, maintain, and extend.

5️⃣ Database Layer (PostgreSQL)

Stores persistent application data.

Stored Data Includes:

User information

Metric records

System-related data

Why PostgreSQL:
Reliable relational database with strong support for structured data.

6️⃣ Utilities Layer

This layer provides cross-cutting support services.

Components:

Validation

Logging

Error Handling

Responsibilities:

Validate incoming requests

Log system events and requests

Handle exceptions centrally

Advantage:
Improves system reliability and debugging without cluttering core logic.

🔁 Data Flow Explanation

Client sends an HTTP request

API Layer receives and validates the request

Service Layer processes business logic

Repository Layer performs database operations

Database stores or retrieves data

Response flows back to the client

Logs and errors are handled via the Utilities layer

🎯 Key Design Principles Used

Separation of Concerns

Layered Architecture

Modular Service Design

Maintainability and Scalability

Clean Data Flow
