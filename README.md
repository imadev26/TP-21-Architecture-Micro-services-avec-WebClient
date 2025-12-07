# TP 21 - Architecture Microservices avec WebClient

## 🎯 Description

Projet d'architecture microservices avec Spring Cloud Eureka et WebClient pour la communication inter-services.

## 🏗️ Architecture

### Services
- **Eureka Server** (Port 8761) - Service de découverte
- **Service Client** (Port 8081) - Gestion des clients avec MySQL
- **Service Car** (Port 8082) - Gestion des voitures avec enrichissement de données

### Technologies
- Spring Boot 3.2.0
- Spring Cloud Eureka
- Spring Data JPA
- MySQL
- WebClient (WebFlux)
- Spring Cloud LoadBalancer

## 🚀 Démarrage

### Prérequis
- Java 17+
- Maven
- MySQL (port 3306)

### Lancement (ordre important)

```bash
# 1. Eureka Server
cd eureka-server
mvn spring-boot:run

# 2. Service Client
cd service-client
mvn spring-boot:run

# 3. Service Car
cd service-car
mvn spring-boot:run
```

### Vérification
- Dashboard Eureka: http://localhost:8761
- API Client: http://localhost:8081/api/clients
- API Car: http://localhost:8082/api/cars

## 📸 Preuve de fonctionnement

![Preuve de fonctionnement](preuve.png)

## 📋 Endpoints API

### Service Client (8081)
- `GET /api/clients` - Liste tous les clients
- `GET /api/clients/{id}` - Client par ID
- `POST /api/clients` - Créer un client

### Service Car (8082)
- `POST /api/cars` - Créer une voiture
- `GET /api/cars` - Liste enrichie (car + client)
- `GET /api/cars/byClient/{clientId}` - Voitures par client
- `GET /api/test/client/{id}` - Test WebClient

## 🔧 Configuration

### Bases de données
- `clientservicedb` (service-client)
- `carservicedb` (service-car)

Les bases sont créées automatiquement au démarrage (`createDatabaseIfNotExist=true`).

## 📦 Postman Collection

Importer `TP21-Postman-Collection.json` pour tester tous les endpoints.

## 👨‍💻 Auteur

**Imad ADAOUMOUM**

## 📄 License

Ce projet est réalisé dans un cadre académique.
