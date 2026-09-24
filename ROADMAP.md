# .NET Backend and AI Engineering Roadmap

The goal is not to know every technology equally deeply.

The roadmap prioritizes the knowledge needed to become a strong **.NET backend engineer capable of designing, implementing, diagnosing, and operating production systems**, while gradually adding distributed systems, cloud, data, and AI engineering.

**Validated baseline (23 September 2026):** .NET 10 LTS and C# 14 are the current stable baseline for this roadmap. .NET 11 is currently at Release Candidate 1 and is not yet generally available.

# Priority system

| Priority | Meaning |
|---|---|
| **P0 — Essential** | Expected knowledge for a competent mid-level .NET backend developer |
| **P1 — Required** | Important for senior-level work and production responsibility |
| **P2 — Specialisation** | Environment-, architecture-, or role-dependent knowledge |
| **P3 — Project-triggered** | Learn when a concrete project requires it |

---

# 1. Modern C# and .NET

## P0 — Professional C# fundamentals

- [ ] Value types vs reference types
- [ ] Object allocation and copying semantics
- [ ] Boxing and unboxing
- [ ] `class` vs `struct`
- [ ] `record` vs `class`
- [ ] `record struct`
- [ ] Value equality vs reference equality
- [ ] Immutability
- [ ] `readonly`, `init`, `required`
- [ ] Nullable reference types
- [ ] Null-state analysis
- [ ] Generics
- [ ] Generic constraints
- [ ] Covariance and contravariance
- [ ] Delegates
- [ ] `Action` / `Func`
- [ ] Events
- [ ] Lambdas
- [ ] Closures
- [ ] Expression trees
- [ ] LINQ
- [ ] Deferred execution
- [ ] Multiple enumeration
- [ ] `IEnumerable<T>` vs `IQueryable<T>`
- [ ] LINQ projections, grouping and joins
- [ ] Pattern matching
- [ ] `switch` expressions
- [ ] `IDisposable`
- [ ] `IAsyncDisposable`
- [ ] Resource ownership
- [ ] `Span<T>`
- [ ] `ReadOnlySpan<T>`
- [ ] `Memory<T>`
- [ ] `ReadOnlyMemory<T>`
- [ ] `ArrayPool<T>`
- [ ] Attributes
- [ ] Reflection fundamentals
- [ ] Source-generation fundamentals
- [ ] Modern C# / C# 14 features relevant to backend development

## P0 — Async and concurrency

- [ ] `async` / `await`
- [ ] How async state machines work conceptually
- [ ] I/O-bound vs CPU-bound work
- [ ] `Task`
- [ ] `Task<T>`
- [ ] `ValueTask`
- [ ] When `ValueTask` is actually appropriate
- [ ] Cancellation
- [ ] `CancellationToken`
- [ ] Cancellation-token propagation
- [ ] Timeouts
- [ ] Avoiding sync-over-async
- [ ] `Task.WhenAll`
- [ ] `Task.WhenAny`
- [ ] Parallel vs concurrent execution
- [ ] Bounded concurrency
- [ ] Race conditions
- [ ] Thread safety
- [ ] `lock`
- [ ] `SemaphoreSlim`
- [ ] Concurrent collections
- [ ] `Channel<T>`
- [ ] Thread-pool starvation
- [ ] `Parallel.ForEachAsync`

## P1 — Runtime and diagnostics

- [ ] CLR architecture
- [ ] IL / JIT
- [ ] Stack vs managed heap
- [ ] Garbage collection
- [ ] GC generations
- [ ] Large Object Heap
- [ ] Allocation pressure
- [ ] Finalization
- [ ] Server GC
- [ ] Runtime counters
- [ ] `dotnet-counters`
- [ ] `dotnet-trace`
- [ ] `dotnet-dump`
- [ ] `dotnet-gcdump`
- [ ] Memory dumps
- [ ] Allocation profiling
- [ ] BenchmarkDotNet
- [ ] Correct benchmarking methodology

### Definition of done

You should be able to explain:

- why a particular type should be a class, record or struct;
- where allocations occur;
- where asynchronous boundaries exist;
- how cancellation travels from HTTP → application → database/HTTP client;
- what happens if 100 requests hit the same code concurrently;
- why a particular synchronization mechanism is or is not necessary.

---

# 2. ASP.NET Core and API Engineering

## P0 — ASP.NET Core fundamentals

- [ ] Application startup and hosting model
- [ ] `WebApplicationBuilder`
- [ ] Middleware pipeline
- [ ] Routing
- [ ] Controllers
- [ ] Minimal APIs
- [ ] Endpoint routing
- [ ] Model binding
- [ ] Model validation
- [ ] Filters
- [ ] Dependency Injection
- [ ] Configuration
- [ ] Options pattern
- [ ] Environment-specific configuration
- [ ] User Secrets
- [ ] Structured logging
- [ ] Exception handling
- [ ] `ProblemDetails`
- [ ] OpenAPI document generation (`Microsoft.AspNetCore.OpenApi`)
- [ ] API documentation/testing UI tooling (Swagger UI / Scalar)
- [ ] Hosted/background services
- [ ] Health checks

## P0 — Dependency Injection

- [ ] Dependency inversion
- [ ] Constructor injection
- [ ] `Transient`
- [ ] `Scoped`
- [ ] `Singleton`
- [ ] Lifetime mismatches
- [ ] Captive dependencies
- [ ] Composition root
- [ ] Factories
- [ ] Why Service Locator is usually undesirable

## P0 — HTTP and REST

- [ ] HTTP request/response lifecycle
- [ ] GET / POST / PUT / PATCH / DELETE
- [ ] Safe methods
- [ ] Idempotency
- [ ] HTTP status codes
- [ ] Headers
- [ ] Content negotiation
- [ ] REST resource modelling
- [ ] URI design
- [ ] Filtering
- [ ] Sorting
- [ ] Pagination
- [ ] Validation errors
- [ ] API versioning
- [ ] DTOs
- [ ] API models vs domain models

## P0 — Outbound HTTP

- [ ] `HttpClient`
- [ ] `IHttpClientFactory`
- [ ] Typed clients
- [ ] Connection reuse
- [ ] Timeouts
- [ ] Cancellation
- [ ] Serialization
- [ ] Retry safety
- [ ] Socket exhaustion fundamentals

## P1 — Production API engineering

- [ ] Rate limiting
- [ ] Output caching
- [ ] Response compression
- [ ] Streaming responses
- [ ] Request streaming
- [ ] Idempotency keys
- [ ] ETags
- [ ] Conditional requests
- [ ] Optimistic HTTP concurrency
- [ ] Resilience policies
- [ ] Retry
- [ ] Timeout
- [ ] Circuit breaker
- [ ] Bulkhead/concurrency limiting
- [ ] API backward compatibility
- [ ] API gateway concepts

## P2

- [ ] gRPC
- [ ] GraphQL
- [ ] WebSockets
- [ ] Server-Sent Events
- [ ] Advanced ASP.NET hosting customization

### Definition of done

Build an API where you can justify:

- every HTTP status code;
- every dependency lifetime;
- every timeout;
- every retry;
- every DTO boundary;
- cancellation propagation;
- exception-to-response mapping.

---

# 3. SQL Server and Data Engineering

## P0 — Relational fundamentals

- [ ] Tables, rows and relations
- [ ] Primary keys
- [ ] Foreign keys
- [ ] Constraints
- [ ] Normalisation
- [ ] Denormalisation and when it is justified
- [ ] Joins
- [ ] Aggregations
- [ ] Subqueries
- [ ] CTEs
- [ ] Window functions
- [ ] Transactions
- [ ] ACID
- [ ] Isolation levels
- [ ] Blocking
- [ ] Deadlocks
- [ ] Lock escalation
- [ ] Optimistic concurrency
- [ ] Pessimistic concurrency
- [ ] SQL injection
- [ ] Parameterisation

## P0 — Indexes and query performance

- [ ] Clustered indexes
- [ ] Non-clustered indexes
- [ ] Composite indexes
- [ ] Covering indexes
- [ ] Included columns
- [ ] Index selectivity
- [ ] SARGability
- [ ] Execution plans
- [ ] Statistics
- [ ] Cardinality estimation fundamentals

## P0 — Entity Framework Core

- [ ] `DbContext`
- [ ] Entity configuration
- [ ] Fluent API
- [ ] Relationships
- [ ] Migrations
- [ ] Change tracking
- [ ] `AsNoTracking`
- [ ] DTO projection
- [ ] Eager / explicit / lazy loading
- [ ] N+1 queries
- [ ] Single vs split queries
- [ ] Transactions
- [ ] Savepoints
- [ ] Concurrency tokens
- [ ] `DbUpdateConcurrencyException`
- [ ] `ExecuteUpdate`
- [ ] `ExecuteDelete`
- [ ] Interceptors
- [ ] Query tags
- [ ] Compiled queries

## P1 — Database performance

- [ ] Inspect generated SQL
- [ ] Read execution plans
- [ ] Detect missing indexes
- [ ] Detect unused/overlapping indexes
- [ ] Reduce round trips
- [ ] Bound result sets
- [ ] Connection pooling
- [ ] Bulk operations
- [ ] EF Core vs Dapper
- [ ] EF Core vs raw SQL
- [ ] Database profiling

---

## P1 — PostgreSQL dedicated track

- [ ] PostgreSQL architecture
- [ ] Important SQL Server/PostgreSQL differences
- [ ] PostgreSQL data types
- [ ] Schemas
- [ ] Identity / sequences
- [ ] MVCC
- [ ] Dead tuples
- [ ] `VACUUM`
- [ ] Autovacuum
- [ ] `ANALYZE`
- [ ] `EXPLAIN`
- [ ] `EXPLAIN ANALYZE`
- [ ] Partial indexes
- [ ] Expression indexes
- [ ] GIN / GiST
- [ ] JSONB
- [ ] Advisory locks
- [ ] Npgsql
- [ ] EF Core with PostgreSQL
- [ ] Connection pooling
- [ ] Replication concepts

### PostgreSQL definition of done

You should be able to explain **MVCC/VACUUM**, diagnose a slow query and design indexes without reasoning about PostgreSQL as though it were simply SQL Server with different syntax.

---

## P1 — MongoDB dedicated track

- [ ] Document databases
- [ ] BSON
- [ ] Collections/documents
- [ ] Relational vs document modelling
- [ ] Embedding vs referencing
- [ ] Schema design around access patterns
- [ ] CRUD operations
- [ ] Query operators
- [ ] Indexes
- [ ] Compound indexes
- [ ] Aggregation pipeline
- [ ] Pagination
- [ ] MongoDB .NET Driver
- [ ] Serialization
- [ ] Transactions
- [ ] Read concern / write concern
- [ ] Replica sets
- [ ] Change Streams

## P2 — MongoDB advanced

- [ ] Sharding
- [ ] Shard-key selection
- [ ] Large-scale MongoDB architecture

### MongoDB definition of done

You should be able to decide whether data belongs in a relational or document model and correctly choose **embedding vs referencing**.

---

## P1 — Elasticsearch / OpenSearch dedicated track

- [ ] Search engines vs databases
- [ ] Documents
- [ ] Indexes
- [ ] Mappings
- [ ] Inverted indexes
- [ ] `text` vs `keyword`
- [ ] Analyzers
- [ ] Tokenization
- [ ] Full-text queries
- [ ] Term queries
- [ ] Filters
- [ ] Relevance/scoring
- [ ] Aggregations
- [ ] Pagination
- [ ] .NET client
- [ ] Bulk indexing

## P2

- [ ] Shards
- [ ] Replicas
- [ ] Index aliases
- [ ] Reindexing
- [ ] Index templates
- [ ] Index lifecycle management
- [ ] Custom analyzers
- [ ] Advanced relevance tuning

### Search definition of done

You should understand why Elasticsearch/OpenSearch is **not normally your source-of-truth database**, and be able to design an index around search requirements.

---

# 4. Testing and Software Quality

## P0 — Testing fundamentals

- [ ] Unit tests
- [ ] Integration tests
- [ ] End-to-end tests
- [ ] Test pyramid as a guideline
- [ ] xUnit
- [ ] Arrange / Act / Assert
- [ ] Parameterized tests
- [ ] Async testing
- [ ] Exception testing
- [ ] Deterministic tests

## P0 — Test doubles

- [ ] Stub
- [ ] Mock
- [ ] Fake
- [ ] When mocking is appropriate
- [ ] Why excessive mocking creates brittle tests
- [ ] Mock boundaries rather than implementation details

## P1 — Integration testing

- [ ] `WebApplicationFactory`
- [ ] ASP.NET Core integration tests
- [ ] Database integration tests
- [ ] Testcontainers
- [ ] External-service test doubles
- [ ] Fixture management
- [ ] Contract testing
- [ ] Testing concurrency
- [ ] Testing failure scenarios

## P2

- [ ] Property-based testing
- [ ] Mutation testing
- [ ] Load testing
- [ ] Chaos testing

### Definition of done

For a feature, you should be able to decide:

**what deserves a unit test, what deserves an integration test, and what should not be mocked.**

---

# 5. Architecture and Domain Modelling

## P0 — Core architectural principles

- [ ] Separation of concerns
- [ ] Cohesion
- [ ] Coupling
- [ ] Dependency inversion
- [ ] Dependency direction
- [ ] Application logic vs domain logic
- [ ] Domain logic vs orchestration logic
- [ ] Transaction boundaries
- [ ] Module boundaries

## P0 — Domain-Driven Design

- [ ] Entity
- [ ] Value Object
- [ ] Aggregate
- [ ] Aggregate Root
- [ ] Repository
- [ ] Domain Service
- [ ] Application Service
- [ ] Domain Event
- [ ] Integration Event
- [ ] Invariants
- [ ] Aggregate consistency boundaries
- [ ] Bounded Context
- [ ] Ubiquitous Language
- [ ] Anemic vs rich domain model

## P0 — Architectural styles

- [ ] Layered architecture
- [ ] Clean Architecture
- [ ] Hexagonal Architecture / Ports & Adapters
- [ ] Modular Monolith
- [ ] Vertical Slice Architecture
- [ ] CQRS
- [ ] MediatR
- [ ] Event-driven architecture
- [ ] Microservices
- [ ] Event Sourcing fundamentals

### Required judgement

You should be able to answer:

- When is CRUD sufficient?
- When does DDD add real value?
- When is DDD unnecessary ceremony?
- Do I actually need a repository over EF Core?
- Does CQRS justify itself here?
- Does this application need MediatR?
- Does Clean Architecture improve this system or merely add layers?
- Should this system remain a modular monolith?
- Why would I split this into microservices?
- Should a domain event be published before or after commit?
- Do I need an Outbox?

## P1 — Strategic architecture

- [ ] Context mapping
- [ ] Anti-Corruption Layer
- [ ] Integration boundaries
- [ ] Module contracts
- [ ] Architecture tests
- [ ] Vertical slices within a modular architecture
- [ ] Eventual consistency between bounded contexts

### Practical architecture project

Use **StrikeOps** to document:

- bounded contexts;
- aggregates;
- invariants;
- transaction boundaries;
- domain events;
- integration events;
- module references;
- why each abstraction exists;
- what could be simplified.

---

# 6. Distributed Systems, Concurrency and Messaging

## P0 — Distributed-system fundamentals

- [ ] Network failure
- [ ] Timeouts
- [ ] Partial failure
- [ ] Ambiguous outcomes
- [ ] Latency
- [ ] Consistency
- [ ] Availability
- [ ] Partition tolerance
- [ ] Eventual consistency
- [ ] At-most-once delivery
- [ ] At-least-once delivery
- [ ] Why "exactly once" requires qualification
- [ ] Duplicate messages
- [ ] Idempotency
- [ ] Correlation IDs
- [ ] Causation IDs
- [ ] Retries
- [ ] Exponential backoff
- [ ] Jitter
- [ ] Poison messages
- [ ] Dead-letter queues

## P0 — Reliability patterns

- [ ] Transactional Outbox
- [ ] Inbox / deduplication
- [ ] Idempotent consumers
- [ ] Saga fundamentals
- [ ] Orchestration vs choreography
- [ ] Distributed locks
- [ ] Distributed-lock failure modes
- [ ] Optimistic vs pessimistic locking

---

## P0 — RabbitMQ dedicated track

- [ ] Producer
- [ ] Consumer
- [ ] Connection
- [ ] Channel
- [ ] Exchange
- [ ] Queue
- [ ] Binding
- [ ] Routing key
- [ ] Direct exchange
- [ ] Topic exchange
- [ ] Fanout exchange
- [ ] Header exchange
- [ ] Consumer acknowledgements
- [ ] `ack`
- [ ] `nack`
- [ ] Requeue
- [ ] Prefetch
- [ ] Durable queues
- [ ] Persistent messages
- [ ] Dead-letter exchanges
- [ ] Retry / delayed redelivery
- [ ] .NET RabbitMQ client

## P1 — RabbitMQ production topics

- [ ] Publisher confirms
- [ ] Quorum queues
- [ ] Poison-message handling
- [ ] Competing consumers
- [ ] Idempotent consumers
- [ ] Connection/channel management
- [ ] Monitoring
- [ ] Security
- [ ] Clustering fundamentals

### RabbitMQ definition of done

Design a workflow that remains correct when:

- the consumer crashes;
- a message is delivered twice;
- processing partially succeeds;
- RabbitMQ temporarily disappears.

---

## P1 — Kafka dedicated track

- [ ] Kafka as a distributed log
- [ ] Broker
- [ ] Topic
- [ ] Partition
- [ ] Record
- [ ] Offset
- [ ] Producer
- [ ] Consumer
- [ ] Consumer group
- [ ] Partition ordering
- [ ] Retention
- [ ] Replay
- [ ] Consumer offsets
- [ ] Rebalancing
- [ ] .NET Kafka client
- [ ] Producer acknowledgements
- [ ] Idempotent producer
- [ ] Kafka transactions
- [ ] Schema management
- [ ] Schema Registry
- [ ] Avro / Protobuf concepts
- [ ] Consumer lag
- [ ] CDC concepts

## P2 — Kafka advanced

- [ ] Kafka Connect
- [ ] Kafka Streams concepts
- [ ] ISR
- [ ] Leader election
- [ ] Replication
- [ ] Partition strategy
- [ ] Exactly-once semantics in Kafka

### Kafka definition of done

You should be able to explain why **Kafka is not simply "RabbitMQ but faster"**, particularly around:

**retention, replay, partitions, offsets, ordering and consumer groups.**

---

## P0 — Networking fundamentals for backend engineers

- [ ] OSI vs TCP/IP at a practical level
- [ ] IP addressing
- [ ] Basic subnetting
- [ ] TCP vs UDP
- [ ] TCP three-way handshake
- [ ] TCP connection lifecycle
- [ ] Ports
- [ ] Sockets
- [ ] Ephemeral ports
- [ ] DNS resolution
- [ ] DNS TTL
- [ ] DNS failure modes
- [ ] HTTP/1.1
- [ ] HTTP/2 multiplexing
- [ ] HTTP connection reuse
- [ ] HTTP/3 / QUIC concepts
- [ ] TLS certificates
- [ ] Certificate authorities
- [ ] Trust chains
- [ ] SNI
- [ ] TLS handshake
- [ ] HTTPS
- [ ] Keep-alive
- [ ] Connection pooling
- [ ] Reverse proxy
- [ ] Forward proxy
- [ ] Load balancer
- [ ] NAT
- [ ] Basic firewall concepts
- [ ] Application/proxy/network timeouts
- [ ] Retry ambiguity
- [ ] `Forwarded`
- [ ] `X-Forwarded-*`

## P1 — Networking diagnostics

- [ ] TCP retransmission
- [ ] TIME_WAIT
- [ ] Connection exhaustion
- [ ] DNS caching
- [ ] TLS termination
- [ ] L4 vs L7 load balancing
- [ ] Sticky sessions
- [ ] CIDR
- [ ] Private/public networks
- [ ] VPN concepts
- [ ] Container networking
- [ ] Kubernetes networking concepts

### Networking definition of done

Trace a production request through:

**DNS → TCP/QUIC → TLS → load balancer/reverse proxy → ASP.NET Core**

and identify where latency, failure and timeouts can occur.

---

# 7. Caching and Performance

## P0 — Caching fundamentals

- [ ] Why caching exists
- [ ] Cache-aside
- [ ] In-memory caching
- [ ] Distributed caching
- [ ] Cache keys
- [ ] TTL
- [ ] Expiration
- [ ] Cache invalidation
- [ ] Stale data
- [ ] Cache stampede
- [ ] Negative caching
- [ ] What should not be cached

---

## P0 — Redis dedicated track

- [ ] Redis architecture
- [ ] In-memory data model
- [ ] Keys
- [ ] TTL / expiration
- [ ] Strings
- [ ] Hashes
- [ ] Lists
- [ ] Sets
- [ ] Sorted Sets
- [ ] Atomic commands
- [ ] Cache-aside with Redis
- [ ] Key naming
- [ ] Serialization
- [ ] `StackExchange.Redis`
- [ ] ASP.NET Core distributed caching
- [ ] Connection reuse
- [ ] Cache failure handling
- [ ] Eviction policies

## P1 — Redis production topics

- [ ] Transactions
- [ ] Optimistic transactions
- [ ] Lua scripting
- [ ] Pub/Sub
- [ ] Redis Streams
- [ ] Consumer groups
- [ ] RDB persistence
- [ ] AOF persistence
- [ ] Replication
- [ ] Sentinel
- [ ] Redis Cluster
- [ ] Distributed coordination
- [ ] Redis locks and their limitations
- [ ] HybridCache
- [ ] Cache stampede prevention
- [ ] Redis diagnostics

### Redis definition of done

You should be able to explain why Redis is **not just a remote `Dictionary<TKey,TValue>`**, and select the appropriate structure, TTL and consistency strategy.

---

## P0 — Performance engineering

- [ ] Latency vs throughput
- [ ] CPU-bound vs I/O-bound bottlenecks
- [ ] Allocation awareness
- [ ] Database bottlenecks
- [ ] Network bottlenecks
- [ ] Measure before optimizing
- [ ] Benchmarking
- [ ] Profiling
- [ ] Connection pooling
- [ ] Object pooling
- [ ] Avoiding unnecessary allocations

## P1

- [ ] GC analysis
- [ ] Memory profiling
- [ ] Thread-pool starvation
- [ ] Lock contention
- [ ] Load testing
- [ ] Performance regressions

---

# 8. Security

## P0

- [ ] Authentication vs authorization
- [ ] Claims
- [ ] Roles
- [ ] Policy-based authorization
- [ ] JWT
- [ ] Cookies
- [ ] OAuth 2.0 fundamentals
- [ ] OpenID Connect
- [ ] Identity providers
- [ ] Access token vs ID token
- [ ] Password hashing
- [ ] HTTPS
- [ ] CORS
- [ ] CSRF
- [ ] XSS
- [ ] SQL injection
- [ ] Input validation
- [ ] Secret management
- [ ] Least privilege

## P1

- [ ] Authorization Code + PKCE
- [ ] Client Credentials
- [ ] Refresh tokens
- [ ] Token validation
- [ ] Key rotation
- [ ] Fine-grained authorization
- [ ] OWASP API Security risks
- [ ] Rate limiting
- [ ] Secure headers
- [ ] Managed identities

## P2

- [ ] mTLS
- [ ] Zero-trust concepts
- [ ] Advanced identity federation

### Definition of done

You should be able to trace:

**user → identity provider → token → ASP.NET authentication → claims → authorization policy → protected resource**

and explain what each component actually guarantees.

---

# 9. Observability and Production Support

## P0 — Observability

- [ ] Logs
- [ ] Metrics
- [ ] Traces
- [ ] Structured logging
- [ ] Log levels
- [ ] Correlation
- [ ] Distributed trace context
- [ ] Health checks
- [ ] Application Insights
- [ ] OpenTelemetry fundamentals
- [ ] Dashboards
- [ ] Alerts

## P1

- [ ] Distributed tracing
- [ ] Spans
- [ ] Trace propagation
- [ ] Sampling
- [ ] RED metrics
- [ ] USE method
- [ ] SLI
- [ ] SLO
- [ ] Production diagnostics
- [ ] Telemetry-cost considerations

---

## P0 — Linux and production runtime fundamentals

- [ ] Linux filesystem structure
- [ ] Paths
- [ ] Users/groups
- [ ] Permissions
- [ ] Processes
- [ ] PIDs
- [ ] Signals
- [ ] Environment variables
- [ ] stdin/stdout/stderr
- [ ] Shell fundamentals
- [ ] Pipes/redirection
- [ ] `ps`
- [ ] `top` / `htop`
- [ ] `kill`
- [ ] `grep`
- [ ] `find`
- [ ] `curl`
- [ ] `cat`
- [ ] `less`
- [ ] `tail`
- [ ] `chmod`
- [ ] `chown`
- [ ] Open/listening ports
- [ ] Running .NET on Linux
- [ ] `SIGTERM`
- [ ] Graceful shutdown
- [ ] systemd fundamentals

## P1 — Production diagnostics

- [ ] `journalctl`
- [ ] CPU diagnosis
- [ ] Memory diagnosis
- [ ] Disk diagnosis
- [ ] File descriptors
- [ ] `/proc`
- [ ] Network diagnostics
- [ ] DNS diagnostics
- [ ] OOM behavior
- [ ] Resource limits
- [ ] Mounts
- [ ] Containers vs host processes
- [ ] `strace`

### Linux definition of done

Given access to a Linux production host, you should be capable of determining:

**what is running, which ports are open, whether the process is healthy, what resources it consumes, and where its failure is coming from.**

---

# 10. Docker, CI/CD and Cloud

## P0 — Docker

- [ ] Containers vs virtual machines
- [ ] Images
- [ ] Containers
- [ ] Dockerfiles
- [ ] Layers
- [ ] Registries
- [ ] Ports
- [ ] Volumes
- [ ] Environment variables
- [ ] Docker networks
- [ ] `docker build`
- [ ] `docker run`
- [ ] Docker Compose
- [ ] Multi-stage builds
- [ ] `.dockerignore`
- [ ] Containerizing ASP.NET Core
- [ ] Persistent vs ephemeral state
- [ ] Health checks

## P0 — CI/CD

- [ ] Git fundamentals
- [ ] Pull requests
- [ ] Build pipelines
- [ ] Restore
- [ ] Build
- [ ] Test
- [ ] Publish
- [ ] Build artifacts
- [ ] Environment configuration
- [ ] Automated deployment
- [ ] Database migrations during deployment

## P1

- [ ] GitHub Actions / Azure DevOps
- [ ] Docker CI/CD
- [ ] Rollback strategies
- [ ] Deployment slots
- [ ] Blue/green deployments
- [ ] Feature flags
- [ ] Secrets in CI/CD

## P0 — Azure fundamentals

- [ ] Subscription
- [ ] Resource Group
- [ ] App Service
- [ ] Azure SQL
- [ ] Storage Account
- [ ] Application Insights
- [ ] Key Vault
- [ ] Managed Identity
- [ ] Azure networking basics
- [ ] Configuration/deployment basics

## P1

- [ ] Azure Service Bus
- [ ] Azure Functions
- [ ] Azure Container Apps
- [ ] Azure Managed Redis
- [ ] Azure Cache for Redis retirement/migration awareness
- [ ] API Management
- [ ] Azure Monitor
- [ ] Azure App Configuration
- [ ] VNets
- [ ] Private endpoints
- [ ] Scaling

## P2 — Kubernetes / infrastructure

- [ ] Kubernetes fundamentals
- [ ] Pods
- [ ] Deployments
- [ ] Services
- [ ] ConfigMaps
- [ ] Secrets
- [ ] Ingress
- [ ] Rolling deployments
- [ ] Scaling
- [ ] AKS
- [ ] Bicep
- [ ] Terraform
- [ ] Infrastructure as Code
- [ ] GitOps

---

# 11. AI Engineering Fundamentals

The aim here is **backend/software engineering around AI**, not becoming an ML researcher.

## P0 — LLM fundamentals

- [ ] What an LLM is
- [ ] Tokens
- [ ] Context windows
- [ ] Prompting
- [ ] System / user / tool messages
- [ ] Temperature and generation parameters
- [ ] Hallucination
- [ ] Structured output
- [ ] Function/tool calling
- [ ] LLM API integration from .NET
- [ ] Latency
- [ ] Cost

## P0 — Embeddings and RAG

- [ ] Embeddings
- [ ] Semantic similarity
- [ ] Vector search
- [ ] Vector databases
- [ ] Chunking
- [ ] Retrieval
- [ ] RAG architecture
- [ ] Grounding
- [ ] Metadata filtering
- [ ] Prompt injection fundamentals

## P1 — Production AI

- [ ] Hybrid search
- [ ] Reranking
- [ ] RAG evaluation
- [ ] Retrieval evaluation
- [ ] LLM evaluation
- [ ] Tool-using agents
- [ ] Agent loops
- [ ] State
- [ ] Memory
- [ ] Guardrails
- [ ] Semantic Kernel concepts
- [ ] Model abstraction
- [ ] LLM observability
- [ ] AI caching

## P2

- [ ] Fine-tuning
- [ ] Open-weight/local models
- [ ] Advanced agent orchestration
- [ ] MCP
- [ ] Multimodal systems
- [ ] Vector-index internals

## P3

- [ ] Training foundation models
- [ ] Deep ML mathematics
- [ ] GPU infrastructure
- [ ] Distributed model training

### Definition of done

Build a .NET service that can:

**retrieve relevant data → construct grounded context → call an LLM → return structured output → evaluate whether the result was actually good.**

---

# 12. Project Roadmap

Recommended Project Roadmap

The roadmap should not be completed only through isolated lessons.

Your projects should progressively force these concepts into practice.

---

# 13. Suggested 24-Week Execution Order

This is an **ordering guide**, not a deadline.

| Weeks | Main focus |
|---|---|
| **1–3** | Modern C# P0 |
| **4–5** | Async/concurrency + CLR fundamentals |
| **6–8** | ASP.NET Core / HTTP / API engineering |
| **9–11** | SQL Server + EF Core + indexes |
| **12** | Testing |
| **13–15** | Architecture / DDD / CQRS / modular monolith |
| **16–17** | Networking + distributed-system fundamentals |
| **18** | Redis / caching |
| **19–20** | RabbitMQ + Outbox + idempotency |
| **21** | Linux / Docker / production diagnostics |
| **22** | Observability / security |
| **23** | Azure / CI/CD |
| **24** | AI / RAG fundamentals |

The dedicated **PostgreSQL, MongoDB, Kafka and Elasticsearch/OpenSearch** tracks can then be inserted when the project reaches a use case that justifies them.

---

# 14. Topics to Deliberately Postpone

These are useful technologies, but learning them too early produces breadth without depth.

## P2/P3 — Do later

- [ ] Kubernetes internals
- [ ] Service mesh
- [ ] Event Sourcing in depth
- [ ] Complex Kafka operations
- [ ] Advanced MongoDB sharding
- [ ] Advanced Elasticsearch cluster administration
- [ ] Advanced CLR internals
- [ ] Unsafe/high-performance C#
- [ ] Advanced native interop
- [ ] Large-scale cloud networking
- [ ] Multi-region distributed systems
- [ ] Advanced distributed consensus
- [ ] Deep ML mathematics
- [ ] Training neural networks
- [ ] GPU/distributed AI infrastructure

These should **not displace P0 backend fundamentals**.

---

# 15. Highest-Value Priorities for Your Current Level

For your current progression as a .NET backend developer, the highest-return sequence remains:

1. **Modern C# and .NET**
2. **Async/concurrency**
3. **ASP.NET Core / HTTP / API design**
4. **EF Core + SQL + indexes + transactions**
5. **Testing**
6. **DDD / architecture / transaction boundaries**
7. **Networking fundamentals**
8. **Distributed-system fundamentals**
9. **Redis**
10. **RabbitMQ + Outbox + idempotency**
11. **Linux / Docker / production troubleshooting**
12. **Observability**
13. **Security**
14. **Azure / CI/CD**
15. **PostgreSQL**
16. **Kafka**
17. **MongoDB / Elasticsearch where the workload warrants them**
18. **AI / RAG engineering**

The important distinction is that **RabbitMQ, Kafka, Redis, MongoDB, PostgreSQL, Networking, Linux and Elasticsearch/OpenSearch are dedicated learning tracks inside this roadmap**, but they do **not need to become separate top-level roadmap categories**.
