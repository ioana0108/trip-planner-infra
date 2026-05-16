# Changelog – Etapa 2

## Auth Service
- Created ASP.NET Core Web API project
- Added AuthController
- Implemented register endpoint
- Implemented login endpoint
- Added in-memory user storage
- Added password hashing using BCrypt
- Added Dockerfile

## Trip Service
- Created ASP.NET Core Web API project
- Added TripsController
- Implemented create trip endpoint
- Implemented get trips endpoint
- Added in-memory trip storage
- Added Dockerfile

## Infrastructure
- Added docker-compose configuration
- Configured ports for each service
- Verified services using Swagger

## Progress
- Implemented core functionality of the application
- Set up microservices architecture
- Services can run independently and via Docker Compose


# Changelog – Etapa 3

All notable changes for the final stage of the Trip Planner project are documented in this file.

The project is a cloud-native Trip Planner application built using a microservices architecture. It includes a React frontend, multiple backend microservices, persistent storage, API Gateway, monitoring, CI/CD, and Docker Swarm deployment.

## [Final Version] - 2026-05-17

### Added

- Implemented **Frontend Service** using React.
- Added user interface for:
  - user registration
  - user login
  - trip creation
  - viewing existing trips
  - itinerary item creation
  - viewing itinerary items

- Implemented **Auth Service** using ASP.NET Core Web API.
- Added endpoints for:
  - user registration
  - user login
  - service testing
- Added password hashing using BCrypt.
- Integrated Auth Service with PostgreSQL using Entity Framework Core.

- Implemented **Trip Service** using ASP.NET Core Web API.
- Added endpoints for:
  - creating trips
  - viewing trips
  - service testing
- Integrated Trip Service with PostgreSQL using Entity Framework Core.

- Implemented **Itinerary Service** using ASP.NET Core Web API.
- Added endpoints for:
  - creating itinerary items
  - viewing all itinerary items
  - viewing itinerary items by trip
  - service testing
- Integrated Itinerary Service with PostgreSQL using Entity Framework Core.

- Added **PostgreSQL** database for persistent data storage.
- Added database tables for:
  - users
  - trips
  - itinerary items

- Added **pgAdmin** for database management through a web interface.
- Added **Portainer** for Docker container and service management.
- Added **Kong API Gateway** for exposing backend microservices through a single entry point.
- Added separate Kong configuration files for:
  - Docker Compose
  - Docker Swarm

- Added **Prometheus** for monitoring.
- Added **Grafana** as a dashboard for observability.
- Connected Grafana to Prometheus as a data source.

- Added **Dockerfile** for the frontend service.
- Added Docker Compose support for running the full application locally.
- Added Docker Swarm deployment configuration using `docker-stack.yml`.
- Deployed the application in a Docker Swarm cluster with:
  - 1 manager node
  - 2 worker nodes

- Added GitHub Actions workflows for CI/CD.
- Configured automatic build workflows for:
  - Auth Service
  - Trip Service
  - Itinerary Service

### Changed

- Replaced in-memory storage with PostgreSQL persistence for backend services.
- Updated the infrastructure configuration to include all final project components.
- Updated Kong routing to expose Auth, Trip, and Itinerary services through the API Gateway.
- Updated frontend requests to communicate with backend services through Kong.
- Updated README documentation with final setup, deployment, and verification steps.

### Fixed

- Fixed PostgreSQL connection issues inside Docker by using service names instead of `localhost`.
- Fixed Kong routing differences between Docker Compose and Docker Swarm.
- Fixed frontend proxy configuration for communication with Kong.
- Fixed date handling in Trip Service for PostgreSQL compatibility.
- Fixed missing database tables by applying Entity Framework migrations.
- Fixed GitHub Actions workflow path issues for the Itinerary Service.

### Notes

- The application can be run locally using Docker Compose.
- The application can also be deployed using Docker Swarm.
- In WSL, Docker Swarm routes may need to be accessed through the WSL IP instead of `localhost`.
- The project now includes the required cloud-native components: microservices, database, database management tool, API Gateway, Portainer, monitoring dashboard, CI/CD, and Swarm deployment.

### Contributors

- Ioana Rusu – designed, implemented, configured, and integrated all services and infrastructure components.