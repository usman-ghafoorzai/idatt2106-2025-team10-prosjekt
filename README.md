# Krisefikser

## 1. Project title
**Krisefikser** is a full-stack crisis-preparedness web application for Norwegian households.

## 2. Overview
Krisefikser helps users prepare for and manage crisis-related situations through household coordination, emergency storage management, map-based situational awareness, and preparedness-focused learning features.  
The repository is organized as a full-stack university team project with a clear separation between backend and frontend applications.

## 3. Context
This project was developed at NTNU in Spring 2025 as part of **IDATT2106 System Development 2 with Agile Project**.  
It represents an academic team delivery with emphasis on collaboration, iterative development, and software engineering practices.

## 4. What this project demonstrates
- Team-based agile software development in a university setting
- Full-stack architecture with backend/frontend separation
- API-driven integration between client and server
- Authentication and role-aware user flows
- Real-time/event-driven features alongside traditional request/response endpoints
- Automated testing and CI usage in a student software project
- Formal project reporting and handover artifacts

## 5. Features
- User registration, login, and verification-related authentication flow
- Role-based access patterns (including admin-oriented functionality)
- Household creation, invitation, joining, and management
- Emergency storage tracking and preparedness overview
- Map/geospatial features for relevant events and locations
- Notifications and real-time updates (WebSocket/STOMP-based integration)
- Preparedness quiz functionality
- Reflection notes with sharing/visibility options

## 6. Tech stack
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

## 7. Project structure
```text
.
|- backend/   # Spring Boot backend
|- frontend/  # Vue 3 frontend
`- rapport/   # Final report artifacts
```

## 8. How to run
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

## 9. Testing and CI
### Local testing
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
- The repository includes CI pipeline definitions in:
  - `backend/.gitlab-ci.yml`
  - `frontend/.gitlab-ci.yml`
- These pipelines include build/test steps and coverage-oriented reporting workflows.

## 10. Documentation
- Backend technical README: `backend/README.md`
- Frontend source and configuration: `frontend/`
- Final project report artifacts: `rapport/`

## 11. Security and public repository note
This repository is a course project and includes course/demo-oriented configuration patterns.  
It should **not** be treated as production-ready or deployed as-is.  
Before any real-world use, credentials handling, secret management, logging policy, and environment hardening must be reviewed and strengthened.

## 12. Team project note
Krisefikser was developed as a team project with shared responsibility across backend, frontend, testing, and documentation.  
The structure and artifacts reflect collaborative agile work, feature ownership across domains, and integration of multiple subsystems into one delivered product.

## 13. Status
Completed academic project (Spring 2025) and maintained here as a portfolio/reference repository.

