# 🛒 Retail Project (Microservices + Kafka)

This project is a **Retail Management System** built using **Spring Boot** microservices architecture.  
It consists of two main services — `InventoryService` and `OrderService` — that communicate asynchronously through **Apache Kafka**.

---

## 📁 Project Structure

```
RetailProject/
│
├── InventoryService331/
│   ├── src/main/java/com/order/
│   │   ├── InventoryService331Application.java
│   │   └── controller/
│   │       └── InventoryController.java
│   ├── src/main/resources/application.properties
│   └── pom.xml
│
├── OrderService33/
│   ├── src/main/java/com/order/
│   │   ├── OrderService33Application.java
│   │   └── controller/
│   │       └── OrderController.java
│   ├── src/main/resources/application.properties
│   └── pom.xml
│
└── pom.xml (Parent POM)
```

---

## ⚙️ Tech Stack

| Component | Technology |
|------------|-------------|
| Language | Java 17 |
| Framework | Spring Boot |
| Build Tool | Maven |
| Messaging | Apache Kafka |
| Architecture | Microservices |
| IDE | IntelliJ / Eclipse |
| Version Control | Git & GitHub |

---

## 🚀 Microservices Overview

### **1️⃣ Inventory Service**
- Manages product stock details.
- Publishes updates to Kafka topics when stock changes occur.
- Listens to Kafka events to synchronize product data.

### **2️⃣ Order Service**
- Handles customer orders and order processing.
- Sends order requests via Kafka.
- Listens for inventory updates to confirm product availability.

---

## 🔗 Kafka Integration Flow

1. **Order Service** sends a message to a Kafka topic (e.g., `order-topic`) when a new order is created.  
2. **Inventory Service** consumes the message, checks stock availability, and responds through another topic (e.g., `inventory-topic`).  
3. The system ensures **decoupled communication** and **asynchronous order processing**.

---

## ⚡ Getting Started

### 1️⃣ Clone the Repository
```bash
git clone https://github.com/Abhishek-Kanade-23/Kafka-Project.git
cd Kafka-Project
```

### 2️⃣ Start Zookeeper and Kafka
```bash
# Start Zookeeper
zookeeper-server-start.bat config/zookeeper.properties

# Start Kafka Server
kafka-server-start.bat config/server.properties
```

### 3️⃣ Create Required Kafka Topics
```bash
kafka-topics.bat --create --topic order-topic --bootstrap-server localhost:9092
kafka-topics.bat --create --topic inventory-topic --bootstrap-server localhost:9092
```

### 4️⃣ Run Microservices
Open two terminals:
```bash
# Terminal 1
cd InventoryService331
mvn spring-boot:run

# Terminal 2
cd OrderService33
mvn spring-boot:run
```

---

## 🧠 Key Features

✅ Microservice-based architecture  
✅ Kafka-based asynchronous communication  
✅ Loose coupling between services  
✅ Scalable and maintainable design  
✅ RESTful APIs for Order & Inventory management  

---

## 🧩 Future Enhancements

- Add API Gateway for centralized routing  
- Integrate Eureka Server for service discovery  
- Add Docker for containerization  
- Add centralized configuration using Spring Cloud Config  

---

## 🧑‍💻 Author

**Abhishek Rangnath Kanade**  
📍 Pune, India  
💼 MERN / Java Full Stack Developer  
🔗 [GitHub](https://github.com/Abhishek-Kanade-23)

