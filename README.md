# Healthcare Platform

A backend microservices project for managing patient records and coordinating downstream healthcare workflows. Built as a portfolio project to demonstrate Java, Spring Boot, distributed-service communication, and event-driven architecture.

## What it does

- Provides REST endpoints to create, list, update, and delete patient records.
- Validates patient data and prevents duplicate email addresses.
- Creates a billing account through a synchronous gRPC call when a patient is registered.
- Publishes a Protobuf patient-created event to Kafka for asynchronous analytics processing.
- Exposes API documentation through OpenAPI/Swagger UI.

## Architecture

| Service | Responsibility | Integration |
| --- | --- | --- |
| Patient Service | Patient CRUD, validation, and workflow orchestration | REST, PostgreSQL/JPA, gRPC client, Kafka producer |
| Billing Service | Billing-account creation | gRPC server |
| Analytics Service | Consumes patient events for analytics processing | Kafka consumer, Protobuf |

## Tech Stack

Java 21, Spring Boot, Spring Data JPA, PostgreSQL, Apache Kafka, gRPC, Protocol Buffers, Maven, Docker, and OpenAPI/Swagger.

## API

The Patient Service runs on port `4000` and supports:

- `GET /patients`
- `POST /patients`
- `PUT /patients/{id}`
- `DELETE /patients/{id}`

## Project Focus

This project highlights backend engineering fundamentals relevant to production healthcare systems: clear service boundaries, synchronous and asynchronous communication patterns, API validation, persistence, and event-driven processing.
