# Java EE / Jakarta EE Developer Guide

This document serves as a reference guide for building enterprise applications with Java EE (Jakarta EE).

---

## 1. Architectural Overview

Java EE uses a multi-tier structure for enterprise applications:

* **Client Tier:** Web browsers, mobile apps, or desktop clients.
* **Web Tier:** Handles HTTP requests and UI logic (Servlets, JAX-RS, JSF/Faces).
* **Business Tier:** Core business logic, transactions, and background tasks (CDI Beans, EJBs).
* **Enterprise Information System (EIS) Tier:** Databases and messaging brokers (RDBMS, JMS Queues).

---

## 2. Core Specifications & Code Examples

### 2.1 Contexts and Dependency Injection (CDI)
CDI handles component lifecycle and dependency injection across the application.

```java
package com.example.service;

import jakarta.enterprise.context.ApplicationScoped;
import jakarta.inject.Named;

@ApplicationScoped
@Named("greetingService")
public class GreetingService {

    public String getGreeting(String name) {
        return "Hello, " + (name != null ? name : "Developer") + "! Welcome to Java EE.";
    }
}