# Software Development Life Cycle (SDLC)

This document summarizes my understanding of the Software Development Life Cycle (SDLC)
with a **simple project where DevOps practices are clearly visible**.

---

### Project Example Used in This SDLC

#### Teacher Availability API (Simple DevOps Project – NestJS)

> A lightweight backend service built with **NestJS** that allows:

* registering teachers
* defining their availability
* allowing parents to query available teachers
* exposing a health check endpoint

This project is intentionally simple in terms of business features but strong in **DevOps practices**.



### 1. Planning

**Goal:** Define why the software is built and for whom.

#### Key activities:

* Identify the purpose of the application
* Define target users (parents and teachers)
* Define availability and reliability expectations
* Identify technical constraints

#### Deliverables:

* Project vision
* High-level roadmap
* Success metrics (API availability, response time)

#### Applied to the project:

* The API must be always available
* Deployment must be automated
* The system must be easy to monitor



### 2. Requirement Analysis

**Goal:** Define what the system must do.

#### Functional requirements:

* Create and list teachers
* Create and query teacher availability
* Provide a health check endpoint

#### Non-functional requirements:

* Response time < 200ms
* Containerized application
* Environment-based configuration
* Logging and monitoring enabled

#### Deliverables:

* Software Requirements Specification (SRS)
* API endpoints definition

#### Tools:

* Git for version control
* Issues or user stories tracking


#### 3. Design

**Goal:** Define how the system will work.

##### Architecture:

```
Client → NestJS API → Database
```

Client → API (Node.js) → Database


#### Design decisions:
- REST API using **NestJS** (Node.js framework)
- Docker for containerization
- Docker Compose for local orchestration
- Environment variables for configuration

#### Deliverables:
- Architecture diagram
- Dockerfile (NestJS)
- docker-compose.yml


### 4. Implementation (Development)

**Goal:** Build the application.

#### Key activities:
- Develop NestJS modules, controllers, and services
- Write basic unit tests
- Use Git branches and clean commits
- Apply code reviews

#### DevOps practices:
- Continuous Integration (CI)
- Automated tests
- Linting and formatting


### 5. CI/CD Pipeline

**Goal:** Automate build, test, and deployment.

#### Pipeline steps:
1. Run tests
2. Build Docker image
3. Validate container startup
4. Prepare image for deployment

#### Tools:
- GitHub Actions
- Docker
- NestJS CLI

### 6. Deployment

**Goal:** Deliver the application reliably.

#### Key activities:
- Automated deployment using Docker Compose
- Environment separation (dev / prod)
- Configuration through environment variables

#### Deliverables:
- Running containers
- Versioned Docker images


### 7. Maintenance & Monitoring

**Goal:** Ensure system stability and continuous improvement.

#### Key activities:
- Monitor application health
- Collect logs
- Fix bugs and improve performance
- Apply security updates

#### Tools:
- Application health endpoint (`/health`) using NestJS Terminus
- Prometheus & Grafana (basic dashboards)
- Docker logs


### DevOps Role in the SDLC

DevOps is present across all phases of this project:
- Planning: reliability and automation mindset
- Design: container-first architecture
- Implementation: CI and code quality
- Deployment: automated delivery
- Maintenance: monitoring and observability




