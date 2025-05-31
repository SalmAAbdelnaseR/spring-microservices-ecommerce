# spring-microservices-ecommerce

# 🛒 E-Commerce Microservices Platform

A distributed e-commerce application built with Spring Boot microservices architecture, demonstrating modern enterprise patterns and best practices.

## 🏗️ Architecture Overview

This application is built using a microservices architecture pattern with three core services:

```
┌─────────────────┐    ┌─────────────────┐    ┌─────────────────┐
│   User Service  │    │ Product Service │    │  Order Service  │
│                 │    │                 │    │                 │
│                 │    │                 │    │                 │
│                 │    │                 │    │                 │
│                 │    │                 │    │                 │
└─────────────────┘    └─────────────────┘    └─────────────────┘
         │                       │                       │
         └───────────────────────┼───────────────────────┘
                                 │
                    ┌─────────────────┐
                    │   REST APIs     │
                    │ (Inter-service  │
                    │ Communication)  │
                    └─────────────────┘
```

## 🚀 Features

### User Service
- User registration and authentication
- Profile management
- User role management
- Account verification

### Product Service
- Product catalog management
- Category management
- Inventory tracking
- Product search and filtering

### Order Service
- Shopping cart functionality
- Order creation and management
- Order status tracking
- Integration with User and Product services

## 🛠️ Technology Stack

| Technology | Purpose |
|------------|---------|
| **Spring Boot** | Microservices framework |
| **Spring Data JPA** | Data persistence layer |
| **Maven** | Dependency management & build tool |
| **RestTemplate** | Inter-service communication |
| **MapStruct** | Object mapping |
| **Lombok** | Boilerplate code reduction |
| **MySQL** | Database (configurable) |


## 📁 Project Structure

```
ecommerce-microservices/
├── user-service/
│   ├── src/main/java/com/ecommerce/user/
│   │   ├── controller/
│   │   ├── service/
│   │   ├── repository/
│   │   ├── entity/
│   │   ├── dto/
│   │   └── mapper/
│   ├── src/main/resources/
    └── pom.xml
├── product-service/
│   ├── src/main/java/com/ecommerce/product/
│   │   ├── controller/
│   │   ├── service/
│   │   ├── repository/
│   │   ├── entity/
│   │   ├── dto/
│   │   └── mapper/
│   ├── src/main/resources/
    └── pom.xml
├── order-service/
│   ├── src/main/java/com/ecommerce/order/
│   │   ├── controller/
│   │   ├── service/
│   │   ├── repository/
│   │   ├── entity/
│   │   ├── dto/
│   │   └── mapper/
│   ├── src/main/resources/
│   └── pom.xml
└── README.md
```

## 🔧 Prerequisites

- Java 17 or higher
- Maven 3.6+
- MySQL 8.0+ (optional, H2 available for development)
- IDE (IntelliJ IDEA, Eclipse, or VS Code)

## 🚀 Getting Started

### 1. Clone the Repository
```bash
git clone https://github.com/yourusername/ecommerce-microservices-spring.git
cd ecommerce-microservices-spring
```

### 2. Database Setup (Optional)
For MySQL:
```sql
CREATE DATABASE user_service_db;
CREATE DATABASE product_service_db;
CREATE DATABASE order_service_db;
```

### 3. Configuration
Update `application.properties` in each service:

```properties
# Database Configuration
spring.datasource.url=jdbc:mysql://localhost:3306/service_db
spring.datasource.username=your_username
spring.datasource.password=your_password

# JPA Configuration
spring.jpa.hibernate.ddl-auto=update
spring.jpa.show-sql=true

# Server Port (different for each service)
server.port=8081  # User Service
server.port=8082  # Product Service
server.port=8083  # Order Service
```

### 4. Build and Run

 Run Individual Services

# Terminal 1 - User Service
cd user-service
mvn spring-boot:run

# Terminal 2 - Product Service
cd product-service
mvn spring-boot:run

# Terminal 3 - Order Service
cd order-service
mvn spring-boot:run
```

## 📡 API Endpoints

### User Service (Port: 8081)
```
GET    /api/users              - Get all users
GET    /api/users/{id}         - Get user by ID
POST   /api/users              - Create new user
PUT    /api/users/{id}         - Update user
DELETE /api/users/{id}         - Delete user
POST   /api/users/login        - User authentication
```

### Product Service (Port: 8082)
```
GET    /api/products           - Get all products
GET    /api/products/{id}      - Get product by ID
POST   /api/products           - Create new product
PUT    /api/products/{id}      - Update product
DELETE /api/products/{id}      - Delete product
GET    /api/products/category/{category} - Get products by category
```

### Order Service (Port: 8083)
```
GET    /api/orders             - Get all orders
GET    /api/orders/{id}        - Get order by ID
POST   /api/orders             - Create new order
PUT    /api/orders/{id}        - Update order status
GET    /api/orders/user/{userId} - Get orders by user
```



## 🎯 Key Design Patterns Implemented

- **Microservices Architecture**: Loosely coupled, independently deployable services
- **Repository Pattern**: Data access abstraction using Spring Data JPA
- **DTO Pattern**: Data transfer objects for API communication
- **Mapper Pattern**: Object mapping using MapStruct
- **RESTful API Design**: Standard HTTP methods and status codes
- **Separation of Concerns**: Clear layered architecture





