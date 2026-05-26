# fullstack-fitness-microservices

Welcome to the **Fullstack Fitness Microservices Platform**, a production-ready, enterprise-grade system built using a modern decoupled architecture. This project showcases how to design, secure, scale, and orchestrate multiple independent services that communicate seamlessly to deliver intelligent fitness insights.

---

## 🚀 Key Highlights
* **Decoupled Microservices Architecture:** Independent services handling distinct business capabilities.
* **AI-Driven Personalization:** Seamless integration with GenAI to provide intelligent fitness, workout, and nutritional tracking.
* **Production-Grade Security & Messaging:** Secure token-based authentication and reliable asynchronous event-driven communication.

---

## 🛠️ Tech Stack & Ecosystem

### **Frontend**
* **React:** Component-based UI for a dynamic, smooth, and responsive user experience.

### **Backend Frameworks & Tools**
* **Spring Boot:** Core framework used to rapidly build resilient, standalone microservices.
* **Java 23:** Leveraging modern Java compilation and language features for high performance.
* **Maven:** Project management and comprehensive dependency automation.

### **Spring Cloud & Service Orchestration**
* **Spring Cloud Config Server:** Centralized external configuration management across all environments.
* **Eureka Server (Spring Cloud Netflix):** Dynamic service registration and discovery, allowing microservices to locate each other without hardcoded URLs.
* **Spring Cloud Gateway:** A single, unified entry point for routing client requests, handling global logging, and security filters.

### **Security & Identity Management**
* **Keycloak:** Centralized identity provider handling user registration, authentication, and Role-Based Access Control (RBAC).

### **Data & Messaging Layer**
* **RabbitMQ (Spring AMQP):** Message broker managing asynchronous communication between services to guarantee loose coupling.
* **PostgreSQL / MySQL:** Robust relational databases handling persistence per microservice (Database-per-Service pattern).

### **Artificial Intelligence**
* **Google Gemini API:** Powering the core intelligent engine to generate tailored workout plans and providing instant AI fitness coaching.

---

## 📂 Microservices Directory
* `configserver` — Manages centralized external properties.
* `eureka` — Coordinates service registry and active lookup tables.
* `gateway` — Acts as the reverse proxy, security firewall, and request router.
* `userservice` — Manages user profiles, credentials, and onboarding data.
* `activityservice` — Tracks workouts, daily metrics, and fitness logs.
* `aiservice` — Connects with Google Gemini API to analyze metrics and deliver personalized suggestions.
* `fitness-app-frontend` — The client-side React user interface.

---

## ⚙️ Recommended Startup Sequence
To run this distributed architecture locally, start the services in the following order:
1. **Infrastructure Backbones:** Spin up **Keycloak**, **RabbitMQ**, and your relational databases.
2. **Central Configuration:** Start the `configserver` and ensure configurations load smoothly.
3. **Service Directory:** Run the `eureka` server (`http://localhost:8761`).
4. **API Routing Gateway:** Run the `gateway` microservice.
5. **Business Services:** Boot up `userservice`, `activityservice`, and `aiservice`. They will auto-register with Eureka.
6. **User Interface:** Run the React `fitness-app-frontend`.
