# Takeaway Cloud Platform

A **reactive**, **microservice-based** food delivery backend built with Spring Cloud, Kafka, Redis, and Docker. Designed to manage food orders, user authentication, menu items, and reviews in a scalable, fault-tolerant, and cloud-native environment.

---

### 🌐 Overview

This system provides backend infrastructure for a Takeaway food delivery service using microservices architecture & supports:

- Horizontal scalability
- Decentralized configuration
- Observability and tracing
- Fault tolerance and resilience

![diagram-export-5-15-2025-10_01_38-PM](https://github.com/user-attachments/assets/8f1875cd-ae41-4ca2-8b73-8ba56e5e4ebf)

---

### ✅ Core Responsibilities

- Menu management for the online café
- User registration, authentication & role management
- Order placement and processing
- User reviews for menu items
- Data provisioning for frontend consumption

---

### 🧰 Technology Stack

- **Framework:** Spring Boot, Spring Cloud
- **Reactive REST APIs:** WebFlux
- **Messaging:** Apache Kafka
- **Configuration Management:** Spring Cloud Config
- **Service Discovery & Routing:** Eureka, Spring Cloud Gateway
- **Resilience & Load Balancing:** Resilience4j, Spring Cloud LoadBalancer
- **Caching:** Redis
- **Tracing & Logging:** Sleuth, Zipkin, Logback (ELK planned)
- **Persistence:** PostgreSQL / MongoDB (for reactive use cases)
- **Containerization:** Docker, Docker Compose
- **API Documentation:** SpringDoc OpenAPI (Swagger)

---

### 🧩 Microservices Architecture

Each service is independently deployable and follows the 12-Factor App principles:

- **User Service** – Manages users, roles, and authentication
- **Menu Service** – Handles dishes, categories, and pricing
- **Order Service** – Processes food orders with reliable messaging
- **Review Service** – Manages user-generated dish reviews
- **Notification Service** – Sends real-time updates via Kafka
- **API Gateway** – Routes client requests, enforces security, and applies rate limiting

---

### 🛠️ Infrastructure Components

- **Config Server** – Centralized configuration
- **Eureka Server** – Service registry and discovery
- **Kafka Broker** – Asynchronous event streaming
- **Redis** – Distributed caching
- **Zipkin** – Distributed tracing for latency monitoring

---

### 🚀 Key Highlights

- ⚡ Reactive programming with **Spring WebFlux**
- 📬 Asynchronous messaging using **Kafka**
- 🛡️ Secure JWT-based authentication with gateway-level enforcement
- 🔄 Circuit Breaker support via **Resilience4j**
- 🧭 Service discovery & routing via **Eureka + API Gateway**
- 🐳 Full containerization with **Docker & Docker Compose**

---

### 🧪 Running the Project with Docker

1. **Clone the repository:**
   ```bash
   git clone https://github.com/your-org/takeaway-cloud-platform.git
   cd takeaway-cloud-platform
   ```

2. **Build and start services:**
   ```bash
   ./mvnw clean package -DskipTests
   docker-compose up --build
   ```

---

### 🧱 Available Docker Services

- `config-server` – Centralized configuration
- `eureka-server` – Service discovery registry
- `gateway-service` – API Gateway
- `user-service`, `order-service`, `menu-service`, `review-service`
- `notification-service`, `kafka`, `zookeeper`, `redis`, `zipkin`, `postgres`

---

### 📐 12-Factor App Practices

| Principle                  | Implementation Example |
|---------------------------|------------------------|
| One Codebase              | Each service in a separate module |
| Explicit Dependencies     | Maven for all declared dependencies |
| Config in Environment     | Spring Cloud Config + environment variables |
| Backing Services          | Redis, Kafka, PostgreSQL via external config |
| Build, Release, Run       | Dockerfile + multi-stage builds |
| Stateless Processes       | Services are stateless, with external persistence |
| Port Binding              | Embedded Netty via WebFlux |
| Concurrency               | Horizontal scaling using containers |
| Dev/Prod Parity           | Identical Docker environments |
| Logs as Event Streams     | Logs to stdout (ELK stack planned) |
| Admin Processes           | CLI tools in separate admin modules |

---

### 🧬 Microservice Design Patterns

- **Service Discovery:** Eureka
- **API Gateway:** Spring Cloud Gateway
- **Externalized Config:** Spring Cloud Config
- **Distributed Tracing:** Sleuth + Zipkin
- **Log Aggregation:** Planned with ELK Stack
- **Circuit Breakers:** Resilience4j
- **Transactional Outbox Pattern:** Kafka + DB coordination

---

### 📁 Project Structure

```
takeaway-cloud-platform/
├── config-server/
├── eureka-server/
├── gateway-service/
├── user-service/
├── order-service/
├── menu-service/
├── review-service/
├── notification-service/
├── common-lib/
└── docker-compose.yml
```

---

### 🔐 Authentication & Authorization

- **Authentication:** Stateless JWT tokens
- **Authorization:** Role-based (CUSTOMER, EMPLOYEE, ADMIN)
- **Security Layer:** Enforced via API Gateway filters

---

### 🤝 Contributing

1. Fork the repository  
2. Create a feature branch  
3. Commit your changes  
4. Open a pull request

---

### 📄 License

This project is licensed under the [MIT License](LICENSE).
