# spring-microservices-ecommerce

# 🛒 E-Commerce Microservices Platform

A distributed e-commerce application built with Spring Boot microservices architecture.

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
- User registration
  
-Get User By ID

-Get User Orders 

### Product Service
- Add Product
- Get Product By ID
- Get All Products

### Order Service
-Create Order 

-Get Order By Id

-Get Order By UserId

-Get Product By Order

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

###  Clone the Repository
```bash
git clone Repo Url
cd spring-microservices-ecommerce
```


###  Configuration
Update `application.properties` in each service:

```properties
# Database Configuration
spring.datasource.url=jdbc:mysql://localhost:3306/springcloud
spring.datasource.username=root
spring.datasource.password=root

# JPA Configuration
spring.jpa.hibernate.ddl-auto=update
spring.jpa.show-sql=true

# Server Port (different for each service)
server.port=8081  # User Service
server.port=8083  # Product Service
server.port=8082  # Order Service
```

###  Build and Run

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



