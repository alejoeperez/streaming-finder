# Architecture Overview

## 1. Purpose
Streaming Finder is a web application that helps users discover where a movie or series is available across multiple streaming platforms.

The first version focuses on a simple and functional end-to-end flow:
- search a title
- view matching results
- open title details
- see streaming providers
- redirect the user to the selected platform

---

## 2. Architectural Style
The system will start as a **modular monolith**.

This means:
- one frontend application
- one backend application
- clear logical separation inside the backend
- simple deployment and development flow

This approach is preferred over microservices in the initial stage because the project is small, learning-focused, and still evolving.

---

## 3. High-Level Components

### Frontend
- Angular web application
- Responsible for user interaction
- Sends requests to backend APIs
- Displays search results and title details

### Backend
- Spring Boot REST API
- Responsible for business logic
- Provides title search and detail endpoints
- Manages internal data access
- Will initially use mocked or manually loaded data

### Database
- PostgreSQL
- Planned as the main persistence layer
- May be introduced after the first functional flow is completed

### External Data Sources
- Not part of the initial MVP implementation
- Will be considered in later phases for real catalog and availability integration

---

## 4. Initial System Flow

1. User enters a title in the Angular frontend
2. Frontend sends a request to the Spring Boot backend
3. Backend searches titles in its current data source
4. Backend returns matching results
5. User selects a title
6. Frontend requests title details
7. Backend returns title details and provider availability
8. User clicks a provider link and is redirected

---

## 5. Initial Design Decisions

### Use Angular for the frontend
Reason:
- It is relevant to the current professional context
- It provides learning value beyond this project

### Use Spring Boot for the backend
Reason:
- It aligns with current backend experience
- It supports fast delivery and strong architectural evolution

### Start with mocked/manual data
Reason:
- Reduces dependency on external APIs
- Keeps the first version focused on core flow
- Avoids early integration complexity

### Start with a modular monolith
Reason:
- Lower complexity
- Easier to understand and evolve
- Better fit for the current size of the project

---

## 6. Planned Evolution

The architecture may evolve later to include:
- PostgreSQL persistence
- Redis caching
- External API integration
- Background synchronization jobs
- Event-driven communication with Kafka
- Cloud deployment in AWS
- Containerization with Docker and orchestration improvements later

---

## 7. Non-Goals for the Initial Version

The first version will not include:
- microservices
- Kubernetes
- RabbitMQ
- authentication
- recommendations
- notifications
- mobile app

These may be considered later only if the core product flow is stable and valuable.

---

## 8. Risks and Open Questions

- Which real data source should be integrated later?
- How should provider availability be refreshed?
- Will content availability differ by region?
- How should broken or outdated provider links be handled?
- When is it justified to introduce caching or async processing?

