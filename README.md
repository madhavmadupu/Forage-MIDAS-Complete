# 🏦 JPMorgan Midas – Virtual Engineering Experience

> A full-stack Spring Boot microservice simulating a real-time financial transaction engine with Kafka event streaming, H2 database persistence, RESTful balance querying, and external incentive integration.

[![Java](https://img.shields.io/badge/Java-17+-ED8B00?logo=java&logoColor=white)](https://openjdk.org/)
[![Spring Boot](https://img.shields.io/badge/Spring_Boot-3.2+-6DB33F?logo=spring&logoColor=white)](https://spring.io/projects/spring-boot)
[![Kafka](https://img.shields.io/badge/Apache_Kafka-3.1+-231F20?logo=apache-kafka&logoColor=white)](https://kafka.apache.org/)
[![H2 Database](https://img.shields.io/badge/H2_Database-2.2+-3C807D?logo=h2&logoColor=white)](https://www.h2database.com/)
[![REST API](https://img.shields.io/badge/REST_API-OpenAPI-0055bb)](https://restfulapi.net/)
[![Maven](https://img.shields.io/badge/Maven-3.8+-C71A36?logo=apache-maven&logoColor=white)](https://maven.apache.org/)

---

## 📌 Overview

This repository contains my implementation for the **JPMorgan Chase – Midas Core Engineering Virtual Experience** (hosted on [Forage](https://www.theforage.com/)). The project simulates a secure, scalable transaction processing system that:

- Ingests financial transactions via **Apache Kafka**
- Validates transactions in real-time
- Persists data using **Spring Data JPA** with an **H2 in-memory database**
- Integrates with an external **Incentive Microservice** via REST
- Exposes a **public REST API** for balance inquiries

Built entirely with **Spring Boot 3**, Java 17, and modern cloud-native patterns, this project demonstrates production-grade software engineering practices including event-driven architecture, transactional integrity, RESTful design, and microservice communication.

---

## 🧩 Core Features & Technical Highlights

| Task | Feature | Technologies Used |
|------|---------|-------------------|
| **1. Project Setup** | Maven-based Spring Boot initialization | Java 17, Spring Boot, Maven |
| **2. Kafka Integration** | Real-time transaction ingestion via Kafka listeners | Spring Kafka, `@KafkaListener`, `ObjectMapper` |
| **3. H2 Database** | ACID-compliant transaction storage & balance management | Spring Data JPA, H2, `@Entity`, `@Transactional` |
| **4. Incentive API** | REST integration with external microservice | `RestTemplate`, JSON serialization, incentive logic |
| **5. REST Controller** | Public `/balance?userId=...` endpoint | `@RestController`, request parameters, JSON response |

### ✅ Key Engineering Practices Demonstrated
- **Event-Driven Architecture**: Decoupled transaction ingestion via Kafka
- **Data Integrity**: Validation before persistence (sender balance ≥ amount)
- **Microservice Communication**: REST client to external incentive service
- **Test-Driven Development**: All logic verified against Forage-provided test suites
- **Production-Ready Configuration**: YAML-based externalized config, proper error handling

---

## 🛠️ Project Structure

```bash
├── src/
│   ├── main/
│   │   ├── java/com/jpmorgan/midas/
│   │   │   ├── MidasApplication.java        # Main Spring Boot app
│   │   │   ├── controller/
│   │   │   │   └── BalanceController.java   # REST endpoint for balances
│   │   │   ├── service/
│   │   │   │   ├── TransactionService.java  # Validation & DB logic
│   │   │   │   └── IncentiveService.java    # REST client to incentive API
│   │   │   ├── listener/
│   │   │   │   └── TransactionListener.java # Kafka message consumer
│   │   │   ├── model/
│   │   │   │   ├── Transaction.java         # Incoming transaction DTO
│   │   │   │   ├── TransactionRecord.java   # JPA-persisted entity
│   │   │   │   ├── User.java                # User with balance
│   │   │   │   └── Balance.java             # API response wrapper
│   │   │   └── repository/
│   │   │       ├── TransactionRecordRepository.java
│   │   │       └── UserRepository.java
│   │   └── resources/
│   │       └── application.yml              # Port, Kafka topic, H2 config
│   └── test/
│       └── java/com/jpmorgan/midas/
│           └── ...                          # Forage-provided test suites
└── pom.xml                                  # Maven dependencies




---

### ✅ How to Use This README
1. Save it as `README.md` in your project root.
2. Replace any placeholder paths if your package structure differs.
3. Add a screenshot of your test success logs if desired (optional but impactful).

This README clearly positions you as a **backend engineer with strong fundamentals in distributed systems**, making it perfect for roles in **Java/Spring, FinTech, or backend development**. Let me know if you'd like a version optimized for LinkedIn or your portfolio site!
