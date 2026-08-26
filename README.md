# Eureka Service Registry

## Student Information
* **Name:** Lahiru Mudith
* **Student Number:** CMS-ST-2026
* **GCP Project ID:** `cms-cloud-architecture`

---

## Service Overview
The **Service Registry** is the central yellow-pages directory for all microservices in the Clinic Management System. Domain services register their dynamic address (host, port, and status) upon boot, allowing client calls and load balancers to route traffic dynamically without hardcoding endpoints.

* **Default Port:** `8761`
* **Technology:** Spring Cloud Netflix Eureka Server.
* **Target Environment:** OpenJDK 25, Spring Boot 4.1.1, Spring Cloud 2025.1.3.

---

## Configuration Bootstrapping
The registry is configured to pull its properties from the Config Server on startup.
It imports properties under the application name `service-registry` using the resource:
[`platform/service-registry.yaml`](file:///C:/Users/Lahiru%20Mudith/Documents/Study/IJSE/4th%20Sem/Enterprise%20Cloud%20Architectur/Projects/Clinic-Management-System/cms-platform/config-server/src/main/resources/configurations/platform/service-registry.yaml)

### Key Configurations:
* `eureka.client.register-with-eureka: false` (Self-registration disabled).
* `eureka.client.fetch-registry: false` (Registry cache fetch disabled).

---

## Dashboard Console
You can monitor all registered microservice instances via the Eureka HTML dashboard:
👉 **[http://localhost:8761](http://localhost:8761)**

---

## Build and Run

### Build Command:
```bash
mvn clean package -DskipTests
```

### Execution Command:
```bash
java -jar target/Service-Registry-1.0.0.jar
```
