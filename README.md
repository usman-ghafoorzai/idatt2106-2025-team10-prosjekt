# Krisefikser

## Overview
Krisefikser is a full-stack crisis-preparedness web application for Norwegian households.

The project focuses on helping users prepare for and manage crisis-related situations through household coordination, emergency storage management, map-based situational awareness, and preparedness-oriented learning features. The repository is organized as a university team project with clear backend/frontend separation.

## Context
This project was developed at NTNU in Spring 2025 as part of **IDATT2106 System Development 2 with Agile Project**.

It represents an academic team delivery with emphasis on collaboration, iterative development, and practical software engineering.

## What This Project Demonstrates
- Team-based agile software development in a university setting
- Full-stack architecture with backend/frontend separation
- API-driven integration between client and server
- Authentication and role-aware user flows
- Real-time and event-driven features alongside standard REST workflows
- Automated testing and CI usage in a student software project
- Formal project reporting and handover artifacts

## Features
- User registration, login, and verification-related authentication flow
- Role-based access patterns, including admin-oriented functionality
- Household creation, invitation, joining, and management
- Emergency storage tracking and preparedness overview
- Map/geospatial features for events and important locations
- Notifications and real-time updates (WebSocket/STOMP-based integration)
- Preparedness quiz functionality
- Reflection notes with sharing and visibility options

## Tech Stack
### Backend
- Java 21
- Spring Boot (REST APIs, Security, Data JPA, WebSocket)
- Maven
- MySQL (development profile) and H2 (test profile)
- OpenAPI/Swagger (API documentation generation)
- JaCoCo (coverage reporting)

### Frontend
- Vue 3 + TypeScript
- Vite
- Pinia + Vue Router
- Tailwind CSS / Vuetify (UI tooling present in project)
- Axios
- Leaflet and related geospatial libraries
- STOMP/SockJS client for real-time updates
- Vitest + Cypress

## Project Structure
```text
.
|- backend/   # Spring Boot backend
|- frontend/  # Vue 3 frontend
`- rapport/   # Final report artifacts
```

## How to Run
The backend and frontend are started separately.

### Prerequisites
- Java 21+
- Maven
- Node.js + npm

### Backend
```bash
cd backend
mvn spring-boot:run -Dspring-boot.run.profiles=dev
```

### Frontend
```bash
cd frontend
npm install
npm run dev
```

### Notes
- Environment variables and local setup details are required for full functionality.
- Detailed backend-specific setup is available in `backend/README.md`.

## Testing and CI
### Local Testing
- Backend tests:
```bash
cd backend
mvn test
```
- Frontend unit tests:
```bash
cd frontend
npm run test:unit
```
- Frontend E2E tests:
```bash
cd frontend
npm run test:e2e
```

### CI
- CI pipeline definitions are included in:
  - `backend/.gitlab-ci.yml`
  - `frontend/.gitlab-ci.yml`
- These pipelines include build and test steps, plus coverage-oriented reporting workflows.

## Documentation
- Backend technical README: `backend/README.md`
- Frontend source and configuration: `frontend/`
- Final project report artifacts: `rapport/`

## Security and Public Repository Note
This repository is a course project and includes course/demo-oriented configuration patterns. It should **not** be treated as production-ready or deployed as-is.

Before any real-world use, credentials handling, secret management, logging policy, and environment hardening must be reviewed and strengthened.

For a concise security/public-repository assessment, see [Security Review](docs/security-review.md).

## Team Project Note
Krisefikser was developed as a team project with shared responsibility across backend, frontend, testing, and documentation.

The structure and artifacts reflect collaborative agile work, feature ownership across domains, and integration of multiple subsystems into one delivered product.

## Status
Completed academic project (Spring 2025), maintained here as a portfolio/reference repository.