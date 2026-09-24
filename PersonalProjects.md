Recommended Project Roadmap

The roadmap should not be completed only through isolated lessons.

Your projects should progressively force these concepts into practice.

## Project 1 — ActorAPI modernization

Focus:

- [ ] Modern C#
- [ ] Async APIs
- [ ] `HttpClientFactory`
- [ ] Dependency Injection
- [ ] Configuration
- [ ] FluentValidation
- [ ] Cancellation
- [ ] Caching
- [ ] Error handling
- [ ] Tests
- [ ] Swagger/OpenAPI
- [ ] Resilience

This remains the smaller project for practicing **modern .NET/API engineering**.

---

## Project 2 — StrikeOps modular monolith

Focus:

- [ ] .NET 10
- [ ] ASP.NET Core
- [ ] EF Core
- [ ] MySQL/PostgreSQL-compatible relational thinking
- [ ] Modular monolith
- [ ] DDD
- [ ] Aggregates
- [ ] Value objects
- [ ] Domain events
- [ ] CQRS
- [ ] MediatR
- [ ] Validation
- [ ] Docker
- [ ] Integration testing
- [ ] Observability

Progressively add:

**Redis → RabbitMQ → background processing → Outbox → idempotent consumers → production diagnostics**

rather than introducing all infrastructure immediately.

---

## Project 3 — Distributed system extension

Once StrikeOps is mature enough:

- [ ] Separate one bounded context/service
- [ ] Introduce asynchronous communication
- [ ] RabbitMQ
- [ ] Transactional Outbox
- [ ] Idempotent consumer
- [ ] Redis
- [ ] Distributed tracing
- [ ] Failure/retry testing
- [ ] Dockerized multi-service environment

Then optionally:

- [ ] Kafka
- [ ] MongoDB
- [ ] Elasticsearch/OpenSearch
- [ ] Kubernetes

The purpose is to encounter **real distributed-system problems**, not manufacture microservices for their own sake.

---

## Project 4 — AI-enabled .NET service

Build a small service using:

- [ ] ASP.NET Core
- [ ] LLM API
- [ ] Embeddings
- [ ] Vector search
- [ ] RAG
- [ ] Structured output
- [ ] Tool calling
- [ ] Evaluation
- [ ] Observability
- [ ] Docker

This gives you practical AI/backend experience without diverting the main roadmap into ML research.
