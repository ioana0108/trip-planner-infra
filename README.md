# Trip Planner – Microservices Project

This project is part of the IDP course and represents a Trip Planner application built using a microservices architecture.

The application allows users to register, log in, create trips, view existing trips, and manage itinerary items for each trip.

## Project Repositories

### Source Code

- Auth Service: https://github.com/ioana0108/trip-planner-auth-service
- Trip Service: https://github.com/ioana0108/trip-planner-trip-service
- Itinerary Service: https://github.com/ioana0108/trip-planner-itinerary-service
- Frontend: https://github.com/ioana0108/trip-planner-frontend

### Infrastructure

- Infrastructure: https://github.com/ioana0108/trip-planner-infra

## Services

- **Frontend Service** – React interface for interacting with the application
- **Auth Service** – handles user registration and login
- **Trip Service** – handles trip creation and viewing existing trips
- **Itinerary Service** – handles itinerary items for trips
- **PostgreSQL** – database used for persistent storage
- **pgAdmin** – database management UI
- **Kong API Gateway** – exposes the microservices through a single gateway
- **Portainer** – UI for managing Docker containers and services
- **Prometheus** – monitoring system
- **Grafana** – dashboard for observability

## Technologies

- React
- ASP.NET Core Web API
- PostgreSQL
- Docker
- Docker Compose
- Docker Swarm
- Kong API Gateway
- Portainer
- Prometheus
- Grafana
- GitHub Actions

## Local development with Docker Compose

To run the project locally using Docker Compose:

```bash
docker compose up --build

The services will be available at:

- Frontend: http://localhost:5173
- Auth Service Swagger: http://localhost:8081/swagger
- Trip Service Swagger: http://localhost:8082/swagger
- Itinerary Service Swagger: http://localhost:8083/swagger
- Kong API Gateway: http://localhost:8000
- pgAdmin: http://localhost:5050
- Portainer: http://localhost:9000
- Prometheus: http://localhost:9090
- Grafana: http://localhost:3000

## Kong routes with Docker Compose

The microservices can be accessed through Kong using:

```text
http://localhost:8000/auth/api/auth/test
http://localhost:8000/trips/api/trips/test
http://localhost:8000/itinerary/api/itinerary/test


## Docker Swarm deployment

The project can also be deployed using Docker Swarm.

## First, make sure the Swarm cluster is active and contains:

1 manager node
2 worker nodes

## Check the nodes with:

docker node ls

## Build the local images:

docker build -t trip-planner-auth-service:latest ../trip-planner-auth-service/TripPlanner.AuthService
docker build -t trip-planner-trip-service:latest ../trip-planner-trip-service/TripPlanner.TripService
docker build -t trip-planner-itinerary-service:latest ../trip-planner-itinerary-service/TripPlanner.ItineraryService
docker build -t trip-planner-frontend:latest ../trip-planner-frontend

## Deploy the stack:

docker stack deploy -c docker-stack.yml trip-planner

##Check the services:

docker stack services trip-planner

## Kong routes with Docker Swarm
## When running through Docker Swarm on WSL, the browser may need the WSL IP instead of localhost.

## Get the WSL IP using:

hostname -I

## Then use the first IP address in the browser:

http://<WSL-IP>:8000/auth/api/auth/test
http://<WSL-IP>:8000/trips/api/trips/test
http://<WSL-IP>:8000/itinerary/api/itinerary/test

## Example:

http://192.168.xxx.xxx:8000/auth/api/auth/test
Database management

## pgAdmin is available at:

http://localhost:5050

## Default credentials:

Email: admin@tripplanner.com
Password: admin

## Database connection inside pgAdmin:

Host: postgres
Port: 5432
Database: trip_planner
Username: postgres
Password: postgres
Monitoring

## Prometheus is available at:

http://localhost:9090

## Grafana is available at:

http://localhost:3000

## Default Grafana credentials:

Username: admin
Password: admin

## Prometheus can be added as a Grafana data source using:

http://prometheus:9090
CI/CD

Each microservice repository contains a GitHub Actions workflow that automatically builds the service on push or pull request to the main branch.

The workflows are configured for:

Auth Service
Trip Service
Itinerary Service