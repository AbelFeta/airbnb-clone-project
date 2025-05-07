# airbnb-clone-project
## 📌 Project Overview

This project is a backend clone of the core features of the Airbnb platform. It is built as part of the ALX Backend Pro course, with a focus on scalable web architecture, RESTful APIs, and backend technologies.

## 🏆 Goals

- User registration and authentication
- Property listing management
- Booking system with check-in/check-out tracking
- Payment processing integration
- Review and rating system

## 🛠️ Tech Stack

- Python
- Django & Django REST Framework
- PostgreSQL
- Docker
- Redis
- Celery
- GraphQL
- GitHub Actions (CI/CD)

## 🚀 Status

Project initialization complete. More features and modules will be added weekly as development progresses.
## 👥 Team Roles

This project involves several key roles, each responsible for different aspects of the backend system. Below is a summary of each role and their responsibilities:

### 🧱 Backend Developer
- Designs and implements the core backend logic.
- Creates and manages API endpoints (REST and GraphQL).
- Ensures data is validated, secure, and optimized.
- Collaborates closely with frontend developers to ensure data flows smoothly.

### 🗃️ Database Administrator (DBA)
- Designs the database schema and ensures normalization.
- Implements indexing, migrations, and query optimization.
- Monitors data integrity and performance.
- Manages backups and restores if needed.

### ⚙️ DevOps Engineer
- Sets up and maintains CI/CD pipelines for smooth deployments.
- Builds and manages Docker containers and orchestrations.
- Configures and monitors system infrastructure and environments.
- Handles scaling, uptime, and performance monitoring.

### 🧪 QA Engineer
- Writes and maintains test cases to ensure quality.
- Performs unit, integration, and performance testing.
- Helps identify bugs and regressions before deployment.
- Collaborates with developers to fix and retest issues.

### 🧠 System Architect (from ITRexGroup reference)
- Plans the system structure, technology stack, and integration points.
- Ensures the architecture supports scalability, security, and flexibility.
- Makes high-level design decisions on services, microservices, and APIs.

- ## 🛠️ Technology Stack

The technology stack used for this project includes the following tools and frameworks:

### 🐍 Python
- **Purpose**: The programming language used to build the backend of the project. Python is known for its simplicity and readability, making it an ideal choice for rapid development.

### 🌐 Django
- **Purpose**: A high-level Python web framework that allows rapid development of secure and maintainable websites. Django will be used to build the backend API (using Django REST Framework) and handle the core business logic.

### 🛠️ Django REST Framework (DRF)
- **Purpose**: An extension of Django that simplifies the process of building RESTful APIs. DRF allows easy creation of endpoints, serialization of data, and handling authentication and permissions.

### 🐘 PostgreSQL
- **Purpose**: A relational database management system (RDBMS) used to store and manage the project's data. PostgreSQL is chosen for its robustness, support for advanced data types, and scalability.

### 🔄 GraphQL
- **Purpose**: A flexible query language for APIs that allows clients to request specific data. In contrast to REST, GraphQL enables more efficient data fetching, making it easier for front-end applications to request only the data they need.

### 🔥 Celery
- **Purpose**: A distributed task queue system used to handle asynchronous tasks such as sending notifications, processing payments, and executing scheduled tasks.

### 🧮 Redis
- **Purpose**: A fast, in-memory data store used for caching and session management. Redis will help speed up the application by reducing the load on the database for frequently accessed data.

### 🐳 Docker
- **Purpose**: A platform that allows you to containerize applications and ensure that the development, testing, and production environments are consistent. Docker will be used for containerizing the app to make deployment easier and more reliable.

### 💻 CI/CD Pipelines
- **Purpose**: Continuous Integration and Continuous Deployment tools (e.g., GitHub Actions) will be used to automate the testing and deployment process. These tools ensure that the project remains bug-free and up-to-date as new changes are pushed.



### 🔐 Security Engineer (optional in advanced teams)
- Implements security policies and encryption.
- Reviews code for vulnerabilities (e.g., SQL injection, XSS).
- Manages authentication systems and monitors threats.

## 🗄️ Database Design

The database for the AirBnB Clone project is designed to manage users, properties, bookings, reviews, and payments. Below is the design for each key entity and how they are related.

### 1. **User**
- **Fields**:
  - `id`: Unique identifier for each user.
  - `email`: The user's email address (used for authentication).
  - `password`: Encrypted password for authentication.
  - `first_name`: First name of the user.
  - `last_name`: Last name of the user.
  - `created_at`: Timestamp for when the user account was created.

- **Relation**: 
  - A **user** can create multiple **properties**.
  - A **user** can have multiple **bookings**.
  - A **user** can leave multiple **reviews**.

### 2. **Property**
- **Fields**:
  - `id`: Unique identifier for each property.
  - `title`: Title or name of the property.
  - `description`: Description of the property.
  - `price_per_night`: Price charged per night for the property.
  - `owner_id`: Foreign key linking to the **user** who owns the property.

- **Relation**: 
  - A **property** belongs to a **user** (owner).
  - A **property** can have multiple **bookings**.
  - A **property** can have multiple **reviews**.

### 3. **Booking**
- **Fields**:
  - `id`: Unique identifier for each booking.
  - `user_id`: Foreign key linking to the **user** who made the booking.
  - `property_id`: Foreign key linking to the **property** being booked.
  - `check_in`: Check-in date for the booking.
  - `check_out`: Check-out date for the booking.
  - `status`: Status of the booking (e.g., confirmed, cancelled).

- **Relation**: 
  - A **booking** belongs to a **user**.
  - A **booking** is associated with one **property**.

### 4. **Review**
- **Fields**:
  - `id`: Unique identifier for each review.
  - `user_id`: Foreign key linking to the **user** who wrote the review.
  - `property_id`: Foreign key linking to the **property** being reviewed.
  - `rating`: Rating given by the user (e.g., 1-5 stars).
  - `comment`: User’s written feedback on the property.

- **Relation**: 
  - A **review** belongs to a **user**.
  - A **review** belongs to a **property**.

### 5. **Payment**
- **Fields**:
  - `id`: Unique identifier for each payment.
  - `booking_id`: Foreign key linking to the **booking** being paid for.
  - `amount`: Total amount of the payment.
  - `payment_date`: Date the payment was made.
  - `payment_status`: Status of the payment (e.g., successful, pending, failed).

- **Relation**: 
  - A **payment** is associated with a **booking**.




