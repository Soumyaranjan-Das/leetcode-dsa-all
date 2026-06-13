# 🚀 4-Month Backend Mastery Roadmap
## Java + Spring Boot → 15–20 LPA | Intermediate → Advanced

> **Your profile:** 2.5 YOE | Java + Spring Boot basics | Daily DSA | Target: 15–20 LPA in 4 months
> 
> **This document is your single source of truth. Follow it strictly. Review it weekly.**

---

## 📋 TABLE OF CONTENTS

1. [Honest Diagnosis](#1-honest-diagnosis)
2. [What To Stop Doing](#2-what-to-stop-doing)
3. [The 4-Month High-Level Plan](#3-the-4-month-high-level-plan)
4. [Week-by-Week Roadmap](#4-week-by-week-roadmap)
5. [Daily Study Structure](#5-daily-study-structure)
6. [Topic-by-Topic Deep Dive](#6-topic-by-topic-deep-dive)
7. [Project Roadmap](#7-project-roadmap)
8. [Interview-Focused Topics](#8-interview-focused-topics)
9. [Tracker Template](#9-tracker-template)
10. [Weekly Review System](#10-weekly-review-system)
11. [Final 4-Month Success Checklist](#11-final-4-month-success-checklist)

---

## 1. HONEST DIAGNOSIS

### Where you actually are right now

You can build a CRUD REST API with Spring Boot. You know @RestController, @Service, @Repository, basic JPA queries, and how to run an app. **That is the starting point, not the destination.**

At 2.5 years with only basics, you are likely doing work your senior fixes or reviews heavily. Interviewers at 15–20 LPA companies know this profile. They will probe you hard on the *why* behind decisions, not just the *how*.

### What 15–20 LPA companies actually test (India, 2024–25)

| Tier | Company Examples | What They Expect |
|------|-----------------|-----------------|
| Product startups | Groww, Zepto, Razorpay, CRED, BrowserStack | Production-grade APIs, distributed systems, system design, clean code |
| MNC product | Google, Walmart, Adobe, Atlassian | Microservices, design patterns, testing, cloud basics |
| Mid-product | Juspay, Simpl, Ola, Swiggy (SDE-2 level) | Spring internals, Kafka/Redis, security, DB performance |

You need **proof of depth**, not just breadth. One great project beats five basic CRUD apps.

---

## 2. WHAT TO STOP DOING

Stop these immediately. They are time sinks with low ROI.

| ❌ Stop Doing | ✅ Replace With |
|---|---|
| Watching Spring Boot beginner tutorials | Reading official docs + Baeldung articles |
| Making notes without building anything | Build while reading. Code first, notes second. |
| Learning Kubernetes before Docker | Docker → CI/CD → then Kubernetes later |
| Studying every design pattern | Learn the 8 critical patterns only |
| Revisiting Java basics (loops, OOP) | You know it. Move forward. |
| Trying to learn everything at once | Follow this sequence strictly |
| Building 10 basic CRUD projects | Build 2 complex production-quality projects |
| Learning Spring Batch, Spring Integration | Not needed for your target role yet |
| Elasticsearch, Cassandra, MongoDB | PostgreSQL + Redis is enough for 4 months |

---

## 3. THE 4-MONTH HIGH-LEVEL PLAN

```
Month 1: Spring Boot Core Mastery + JPA + REST API Design + Clean Code
Month 2: Security + Testing + Microservices Architecture + Docker
Month 3: Kafka + Redis + DB Performance + System Design Fundamentals  
Month 4: CI/CD + Portfolio Polish + Mock Interviews + Job Applications
```

### Skills Stack You Will Have at the End

```
Language:     Java 17+ (Records, Sealed Classes, Streams, CompletableFuture)
Framework:    Spring Boot 3.x (advanced internals, lifecycle, custom config)
Persistence:  Spring Data JPA, Hibernate, PostgreSQL (query tuning, indexing)
Security:     Spring Security 6, JWT, OAuth2 basics
Messaging:    Apache Kafka (producer/consumer, topics, partitions)
Caching:      Redis (caching, TTL, eviction, session management)
Testing:      JUnit 5, Mockito, Testcontainers, Integration Tests
Microservices: Service decomposition, API Gateway, Eureka, OpenFeign
Docker:       Dockerfile, docker-compose, multi-stage builds
CI/CD:        GitHub Actions (build, test, deploy pipeline)
Monitoring:   Spring Actuator, Prometheus, Grafana (basics)
API Design:   REST best practices, versioning, pagination, rate limiting
Architecture: SOLID, 8 core design patterns, Hexagonal Architecture
```

---

## 4. WEEK-BY-WEEK ROADMAP

### ═══ MONTH 1: CORE MASTERY ═══

---

#### WEEK 1 — Spring Boot Advanced Internals

**Goal:** Understand how Spring Boot actually works under the hood

**Topics:**
- Spring Application Context & Bean Lifecycle
- Auto-configuration mechanism (`@EnableAutoConfiguration`, `spring.factories`, `@Conditional`)
- `@SpringBootApplication` internals
- Bean Scopes (Singleton, Prototype, Request, Session)
- Dependency Injection: Constructor vs Field vs Setter (and why constructor wins)
- Profiles (`@Profile`, `application-{env}.yml`, programmatic profile activation)
- `@ConfigurationProperties` vs `@Value` (when to use which)
- Spring Boot Starter anatomy (create your own custom starter as practice)
- `ApplicationEvents` and `ApplicationRunner` / `CommandLineRunner`

**Practice Task:**
- Create a multi-profile Spring Boot project (dev/staging/prod configs)
- Write a custom `@ConfigurationProperties` class for DB + cache config
- Trace what happens from `SpringApplication.run()` to first HTTP request using debug logs

**Deliverable:** GitHub commit: `week-01-spring-internals`

---

#### WEEK 2 — Spring Data JPA & Hibernate (Advanced)

**Goal:** Go from basic CRUD to production-grade database layer

**Topics:**
- Entity lifecycle states (Transient, Managed, Detached, Removed)
- Lazy vs Eager loading — N+1 problem and how to fix it (JOIN FETCH, `@EntityGraph`)
- `@OneToMany`, `@ManyToMany`, `@ManyToOne` — bidirectional vs unidirectional
- Cascade types (when to use CascadeType.ALL vs not)
- JPA Projections (interface-based, class-based, dynamic)
- Specifications API (dynamic queries without writing query strings)
- `@Query` (JPQL + native SQL) — when to use each
- Pagination and Sorting (`Pageable`, `Page<T>`, `Slice<T>`)
- Optimistic vs Pessimistic Locking (`@Version`, `LockModeType`)
- Database transactions — `@Transactional` internals, propagation, isolation levels
- Custom repositories (when `JpaRepository` is not enough)
- Auditing: `@CreatedDate`, `@LastModifiedDate`, `@CreatedBy`

**Practice Task:**
- Model a schema: User → Orders → OrderItems → Products (full relationships)
- Fix a deliberate N+1 problem using JPQL JOIN FETCH
- Write a `Specification`-based dynamic search API (filter by name, status, date range)
- Implement soft delete with `@Where` annotation

**Deliverable:** GitHub commit: `week-02-jpa-advanced`

---

#### WEEK 3 — REST API Design (Production-Grade)

**Goal:** Design APIs like a senior engineer, not a bootcamp grad

**Topics:**
- REST maturity model (Richardson Model — know all 4 levels)
- HTTP methods, status codes (the nuanced ones: 202, 204, 207, 409, 422)
- URI design best practices (plural nouns, no verbs, versioning)
- API versioning strategies (URL, header, media type) — know trade-offs
- Request/Response design: DTOs, separation from entities
- Validation: `@Valid`, `@Validated`, Bean Validation (JSR-380), custom validators
- Global Exception Handling: `@ControllerAdvice`, `@ExceptionHandler`, ProblemDetail (RFC 7807)
- Pagination response format (links, metadata, content)
- Filtering, sorting, searching patterns
- HATEOAS (know what it is; implement basic links)
- Idempotency (idempotency keys for POST APIs — critical for payments/fintech)
- API Rate Limiting (conceptual + Bucket4j implementation)
- Request logging (MDC, correlation IDs for distributed tracing)

**Practice Task:**
- Build a fully RESTful Product Catalog API with: filtering, pagination, sorting, versioning, proper error responses (ProblemDetail format), validation
- Add MDC-based request correlation ID logging
- Document it with SpringDoc OpenAPI (Swagger UI)

**Deliverable:** GitHub commit: `week-03-rest-api-design` (push the Product API)

---

#### WEEK 4 — Clean Code, SOLID, and Design Patterns

**Goal:** Write code that senior engineers won't rewrite after your PR

**Topics:**

**Clean Code (2 days):**
- Meaningful naming (variables, methods, classes)
- Single Responsibility at method level
- Method size discipline (10–15 lines max)
- Avoiding magic numbers/strings
- Comments: why to avoid most of them
- Return early pattern (avoid deep nesting)

**SOLID Principles (2 days) — with Spring examples:**
- SRP: One reason to change
- OCP: Open for extension (Strategy pattern context)
- LSP: Substitutability (understand via example)
- ISP: Interface segregation
- DIP: Depend on abstractions (how Spring DI embodies this)

**8 Critical Design Patterns (3 days) — implement each in Spring:**
1. **Strategy** — payment processor (UPI/Card/Wallet)
2. **Factory/Factory Method** — notification service (Email/SMS/Push)
3. **Builder** — complex object construction
4. **Decorator** — layered logging/caching behavior
5. **Observer** — Spring Events as Observer pattern
6. **Template Method** — report generation
7. **Singleton** — understand via Spring's singleton bean scope
8. **Proxy** — understand via Spring AOP (`@Transactional` is a proxy)

**Practice Task:**
- Refactor your Week 3 Product API: apply SOLID and at least 3 design patterns
- Implement a `NotificationService` using Strategy + Factory patterns
- Write a `PaymentProcessor` interface with 3 implementations

**Deliverable:** Refactored code committed. GitHub commit: `week-04-clean-code-patterns`

---

### ═══ MONTH 2: SECURITY + TESTING + MICROSERVICES ═══

---

#### WEEK 5 — Spring Security 6 + JWT + OAuth2

**Goal:** Implement production-grade authentication and authorization

**Topics:**
- Spring Security 6 architecture: `SecurityFilterChain`, `AuthenticationManager`, `UserDetailsService`
- JWT: structure (header.payload.signature), validation, refresh tokens
- Stateless auth vs session-based auth (when to use which)
- Role-based access control (RBAC): `@PreAuthorize`, `@Secured`, method security
- Permission-based security (custom `PermissionEvaluator`)
- OAuth2 Resource Server configuration (validating tokens)
- OAuth2 Login (Social login: Google — integrate one)
- CORS configuration (production-safe)
- CSRF: when to enable, when to disable (stateless REST = disable)
- Password encoding (`BCryptPasswordEncoder`, Argon2)
- Security headers (CSP, X-Frame-Options, HSTS)
- Token blacklisting/revocation (Redis-based approach)

**Practice Task:**
- Build a full Auth Service: register, login (JWT), refresh token, logout (blacklist in Redis)
- Add role-based access: `ADMIN` can do CRUD, `USER` can only read
- Add Google OAuth2 login
- Secure the Week 3 Product API with JWT

**Deliverable:** GitHub commit: `week-05-spring-security-jwt`

---

#### WEEK 6 — Testing (JUnit 5 + Mockito + Integration Tests)

**Goal:** Write tests that actually prove your code works

**Topics:**

**Unit Testing (2 days):**
- JUnit 5: `@Test`, `@BeforeEach`, `@AfterEach`, `@ParameterizedTest`, `@ExtendWith`
- Mockito: `@Mock`, `@InjectMocks`, `when/then`, `verify`, `ArgumentCaptor`
- Testing service layer in isolation
- Testing edge cases: null inputs, empty lists, boundary values

**Integration Testing (2 days):**
- `@SpringBootTest` — full context vs sliced context
- `@WebMvcTest` — controller layer only
- `@DataJpaTest` — repository layer only
- MockMvc — testing HTTP endpoints without real server
- `@Testcontainers` — spin up real PostgreSQL/Redis for tests
- Testing security (mocking security context)

**Code Quality Tools (1 day):**
- JaCoCo (code coverage reports)
- SonarLint (IDE plugin) — fix real code smells
- Basic Checkstyle config

**Practice Task:**
- Write unit tests for all service classes from previous weeks (target >80% coverage)
- Write integration tests for your Auth API using Testcontainers + PostgreSQL
- Write MockMvc tests for all REST endpoints

**Deliverable:** GitHub commit: `week-06-testing` (all tests green, JaCoCo report showing >75%)

---

#### WEEK 7 — Microservices Architecture + Spring Cloud

**Goal:** Understand microservices patterns and build one multi-service system

**Topics:**

**Concepts (2 days):**
- Monolith vs Microservices: honest trade-offs
- Domain-Driven Design basics: Bounded Context, Aggregates
- Service decomposition principles
- Sync vs Async communication
- API Gateway pattern
- Service discovery pattern
- Circuit Breaker pattern
- Saga pattern (for distributed transactions) — conceptual

**Spring Cloud (3 days):**
- Spring Cloud Gateway (API Gateway)
- Netflix Eureka (Service Discovery: Server + Client)
- OpenFeign (declarative HTTP client between services)
- Resilience4j: `@CircuitBreaker`, `@Retry`, `@RateLimiter` (replace deprecated Hystrix)
- Centralized config: Spring Cloud Config Server
- Distributed tracing: Micrometer + Zipkin/Tempo

**Practice Task:**
- Decompose your application into 3 services: `user-service`, `product-service`, `order-service`
- Add Eureka discovery, API Gateway, Feign clients between services
- Add Circuit Breaker on the order→product service call
- Run all 3 services locally with docker-compose

**Deliverable:** GitHub commit: `week-07-microservices` (3-service app running locally)

---

#### WEEK 8 — Docker (Essentials for a Backend Engineer)

**Goal:** Containerize your applications for production

**Topics:**
- Docker fundamentals: images, containers, layers, volumes, networks
- Writing optimized `Dockerfile`s for Spring Boot (multi-stage builds to reduce image size)
- `.dockerignore` — what to exclude
- `docker-compose.yml` — orchestrate your full local stack
- Docker networking: bridge, host
- Docker volumes for database persistence
- Environment variable injection (secrets, not hardcoded)
- Docker image best practices (non-root user, health checks)
- Pushing images to Docker Hub / GitHub Container Registry
- Intro to container orchestration (why Kubernetes exists — conceptual only)

**Practice Task:**
- Dockerize all 3 microservices from Week 7
- Write a `docker-compose.yml` that starts: user-service + product-service + order-service + PostgreSQL + Redis + Zipkin
- Run your entire stack with a single `docker-compose up`
- Test all APIs via Postman against dockerized stack

**Deliverable:** GitHub commit: `week-08-docker` (docker-compose.yml that boots full stack)

---

### ═══ MONTH 3: DISTRIBUTED SYSTEMS + PERFORMANCE ═══

---

#### WEEK 9 — Apache Kafka (Event-Driven Architecture)

**Goal:** Understand and implement async event-driven communication

**Topics:**
- Kafka fundamentals: topics, partitions, offsets, consumer groups, brokers
- When to use Kafka vs REST (async vs sync trade-offs)
- Spring Kafka: `@KafkaListener`, `KafkaTemplate`, `ProducerFactory`, `ConsumerFactory`
- Serialization: JSON with Avro/Schema Registry basics
- Error handling: Dead Letter Topics (DLT), retry mechanisms
- Idempotent producers (exactly-once semantics — know the concept)
- Consumer group rebalancing
- Kafka Streams — conceptual understanding only
- Monitoring Kafka: consumer lag (critical metric to know)
- Local Kafka setup via Docker

**Practice Task:**
- Add Kafka to your microservices: when an `Order` is placed, publish an `OrderCreatedEvent`
- `notification-service` consumes `OrderCreatedEvent` and logs a notification
- Implement DLT for failed message processing
- Write a consumer group with 3 consumers and see partition assignment

**Deliverable:** GitHub commit: `week-09-kafka` (event-driven order notification flow)

---

#### WEEK 10 — Redis (Caching + Session + Rate Limiting)

**Goal:** Add caching and performance optimization with Redis

**Topics:**
- Redis data structures: Strings, Lists, Sets, Sorted Sets, Hashes, Streams
- Spring Cache abstraction: `@Cacheable`, `@CachePut`, `@CacheEvict`
- Redis as cache: TTL, eviction policies (LRU, LFU)
- Cache-aside vs Write-through vs Write-behind patterns
- Distributed session management with Redis
- Redis Pub/Sub (basics, contrast with Kafka)
- Distributed locking with Redis (Redisson library — `RLock`)
- Rate limiting implementation using Redis sorted sets
- Cache stampede problem and solutions (mutex, probabilistic early expiration)

**Practice Task:**
- Cache product catalog API responses (with proper TTL and eviction)
- Implement distributed rate limiting on your Auth API (100 requests/minute per user)
- Use Redis for JWT token blacklisting (Week 5 task upgraded)
- Implement distributed lock for inventory decrement on order placement

**Deliverable:** GitHub commit: `week-10-redis` (caching + rate limiting demo)

---

#### WEEK 11 — Database Performance & Advanced PostgreSQL

**Goal:** Write queries and design schemas that don't fall apart under load

**Topics:**
- Indexing: B-Tree, Hash, partial indexes, composite indexes, index selectivity
- `EXPLAIN ANALYZE` — read and interpret query plans
- Slow query identification and optimization
- Query optimization: avoid `SELECT *`, use covered indexes
- Database normalization vs denormalization (when to break rules)
- Connection pooling: HikariCP (default in Spring Boot) — tuning configuration
- Database partitioning — conceptual (range, list, hash)
- Read replicas pattern
- Optimistic locking vs Pessimistic locking (practical implementation)
- Database migrations: Liquibase (preferred) vs Flyway
- Stored procedures vs application-level logic (and why to prefer app logic)
- Soft delete patterns and their query performance implications

**Practice Task:**
- Take your order management schema; add 100,000 rows of test data using a data generator
- Identify slow queries using `EXPLAIN ANALYZE`
- Add appropriate indexes; measure before/after query time
- Set up Liquibase for all your schema changes (retroactively migrate existing schemas)
- Tune HikariCP pool size for your application

**Deliverable:** GitHub commit: `week-11-db-performance` (before/after query analysis documented in README)

---

#### WEEK 12 — System Design Fundamentals (Interview-Ready)

**Goal:** Be able to discuss and design systems in interviews confidently

**Topics to Study (concept + diagram):**
- CAP Theorem — when CP vs AP vs CA makes sense
- Horizontal vs Vertical scaling
- Load balancing strategies (Round Robin, Least Connections, IP Hash)
- SQL vs NoSQL — decision framework (not just "NoSQL is faster")
- Caching strategies (CDN, reverse proxy, application, database)
- Message queues: when to use (decoupling, async, spike absorption)
- Rate limiting algorithms (Token Bucket, Leaky Bucket, Sliding Window)
- Database sharding (conceptual: horizontal partitioning)
- Read-heavy vs Write-heavy system design
- Idempotency in distributed systems
- Eventual consistency — what it means in practice

**Systems to Design (practice each one):**
1. URL shortener (Bitly)
2. E-commerce product catalog
3. Order management system
4. Notification service
5. Rate limiter
6. Payment ledger (idempotency focus)

**Practice Task:**
- For each system above: draw a diagram, write component explanations, identify bottlenecks
- Estimate scale: "Design for 100K DAU" → calculate RPS, storage, bandwidth
- Document your 3-microservice design with architecture diagram (use draw.io or Excalidraw)

**Deliverable:** A `system-design-notes.md` file in your GitHub with all 6 systems documented

---

### ═══ MONTH 4: PRODUCTION READINESS + INTERVIEW PREP ═══

---

#### WEEK 13 — CI/CD + Monitoring + Production Hardening

**Goal:** Know how code goes from your laptop to production

**Topics:**

**CI/CD with GitHub Actions (2 days):**
- GitHub Actions: workflows, jobs, steps, triggers
- Build pipeline: compile → test → code quality → Docker build → push image
- Environment-specific deployment configs
- Secrets management in CI/CD
- Branch protection rules

**Monitoring + Observability (2 days):**
- Spring Boot Actuator: health, metrics, info, env endpoints — secure them properly
- Micrometer: custom metrics, Gauges, Counters, Timers
- Prometheus: scraping metrics (docker-compose setup)
- Grafana: dashboards (import Spring Boot dashboard)
- Centralized logging: Loki + Grafana or ELK basics (conceptual)
- Alerting basics

**Production Hardening (1 day):**
- Graceful shutdown in Spring Boot
- Health check endpoints for Docker/Kubernetes
- External secrets management (HashiCorp Vault — conceptual)
- API security hardening checklist

**Practice Task:**
- Build a full GitHub Actions pipeline for one of your microservices
- Set up Prometheus + Grafana with Spring Actuator metrics via docker-compose
- Add custom business metrics (orders per minute, payment failure rate)

**Deliverable:** GitHub commit: `week-13-cicd-monitoring`

---

#### WEEK 14 — Final Project Polish + README + Portfolio Setup

**Goal:** Make your GitHub portfolio ready to impress any interviewer

**Tasks:**
- Polish Project 1 (SmartStore): clean code, tests >75%, proper README, Swagger docs live
- Polish Project 2 (MicroCart): full docker-compose, architecture diagram, README
- Create a pinned GitHub profile with:
  - Profile README (who you are, tech stack, projects)
  - Pinned repos: 2 main projects + system-design-notes + clean-code examples
- Write architecture decision records (ADRs) for key decisions in your projects
- Record a 3-minute demo walkthrough (optional but impressive)
- Update LinkedIn:
  - Headline: "Backend Engineer | Java · Spring Boot · Microservices · Kafka · Redis"
  - Projects section with GitHub links
  - Skills: endorse the right ones

**Deliverable:** Public GitHub profile + 2 complete project repos ready to share

---

#### WEEKS 15–16 — Interview Preparation + Applications

**Goal:** Convert your preparation into offers

**Mock Interviews (every day):**
- Explain your projects (practice STAR method for architecture decisions)
- System design mock: do 1 per day
- Backend concept Q&A: 10 questions per day from the list in Section 8

**Job Applications:**
- Target: 5 quality applications per day (not spray-and-pray)
- Referrals > Cold apply > LinkedIn Easy Apply
- Track everything in your tracker

---

## 5. DAILY STUDY STRUCTURE

### Weekday Schedule (Assuming 3–4 hours/day available after work)

```
Time Block    | Activity                                    | Duration
──────────────|─────────────────────────────────────────── |──────────
Block 1       | DSA (you already do this — keep it)         | 45 min
Block 2       | Read/learn current week's topic (Baeldung,  | 60 min
              | official docs, reflectoring.io)              |
Block 3       | Code + Build (implement what you just read) | 75 min
Block 4       | Review yesterday's code / fix bugs / commit | 30 min
──────────────|─────────────────────────────────────────── |──────────
Total Backend | ~2.75 hours/day                             |
```

### Weekend Schedule (6–8 hours/day)

```
Morning (3 hr): Catch up on week's topics + deep reading
Afternoon (3 hr): Project work (coding, integration, testing)
Evening (1–2 hr): Weekly review + plan next week
```

### Non-negotiable daily habits:
1. **Commit to GitHub every single day** — your streak is your proof
2. **Write one thing you learned in a private notes file** — forces clarity
3. **Don't skip weekends** — that's 50% of your study time

---

## 6. TOPIC-BY-TOPIC DEEP DIVE

### Topic 1: Spring Boot Advanced Internals

**Why it matters:** Every Spring Boot interview question traces back to internals. Interviewers say "you clearly know Spring" only when you explain *why* something works, not just *that* it works.

**Depth required:** Understand auto-configuration mechanism, bean lifecycle hooks, and be able to explain them without notes.

**Best Sources:**
- **Primary:** [Spring Framework Official Docs](https://docs.spring.io/spring-framework/reference/) — read "Core" section
- **Secondary:** [Baeldung — Spring Boot Auto-configuration](https://www.baeldung.com/spring-boot-autoconfiguration) + [Baeldung — Bean Lifecycle](https://www.baeldung.com/spring-bean-lifecycle)
- **Deep dive:** [reflectoring.io — Spring Boot articles](https://reflectoring.io/categories/spring-boot/)
- **Source code:** Browse `spring-boot-autoconfigure` jar — read 5 AutoConfiguration classes

**Build after learning:** Custom Spring Boot Starter for request logging

---

### Topic 2: Spring Data JPA / Hibernate

**Why it matters:** 80% of backend bugs are database-related. N+1 queries, transaction management, locking — these are senior-level problems you must handle.

**Depth required:** Fix N+1 problems instinctively, design correct entity relationships, understand transaction propagation.

**Best Sources:**
- **Primary:** [Thorben Janssen's blog](https://thorben-janssen.com/) — best Hibernate resource on the internet, period
- **Secondary:** [Baeldung — JPA](https://www.baeldung.com/category/persistence/), [Vlad Mihalcea's blog](https://vladmihalcea.com/) (advanced)
- **Book (optional, paid):** "High-Performance Java Persistence" — Vlad Mihalcea
- **Official:** [Spring Data JPA Docs](https://docs.spring.io/spring-data/jpa/reference/)

**Build after learning:** Dynamic search API with Specifications + JPA audit trail

---

### Topic 3: REST API Design

**Why it matters:** This is literally your job. Weak REST design is immediately visible to interviewers. They will ask: "How do you version your API? What status code for X? How do you handle pagination?"

**Depth required:** Design correct, complete APIs independently. Know RFC 7807 ProblemDetail.

**Best Sources:**
- **Primary:** [REST API Design Best Practices — Microsoft Azure Docs](https://learn.microsoft.com/en-us/azure/architecture/best-practices/api-design)
- **Secondary:** [Baeldung — REST API Best Practices](https://www.baeldung.com/rest-with-spring-series)
- **Reference:** [HTTP Status Codes](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status) — know them all
- **Rate limiting:** [Bucket4j GitHub](https://github.com/bucket4j/bucket4j) + Baeldung tutorial

**Build after learning:** Versioned, paginated, validated Product Catalog API

---

### Topic 4: Clean Code + SOLID + Design Patterns

**Why it matters:** At 15–20 LPA, your code is reviewed. Code that violates SOLID gets commented immediately. Knowing design patterns helps you communicate architecture concisely.

**Depth required:** Apply patterns without looking them up. Explain any pattern with a Spring example.

**Best Sources:**
- **Primary:** [Refactoring.Guru](https://refactoring.guru/design-patterns) — best free visual resource for patterns
- **Secondary:** [Baeldung — Design Patterns](https://www.baeldung.com/design-patterns-series)
- **Book (optional, paid):** "Clean Code" by Robert Martin — read Chapters 1–6, 10–11
- **SOLID in Java:** [Digital Ocean SOLID tutorial](https://www.digitalocean.com/community/conceptual-articles/s-o-l-i-d-the-first-five-principles-of-object-oriented-design)

**Build after learning:** Refactor an existing project to apply 3+ patterns

---

### Topic 5: Spring Security 6 + JWT

**Why it matters:** Every production app needs auth. Interviewers ask about JWT internals, refresh token rotation, OAuth2 flows. This is a guaranteed interview topic.

**Depth required:** Build end-to-end auth from scratch without tutorials. Explain JWT vulnerabilities (alg:none attack, etc.).

**Best Sources:**
- **Primary:** [Spring Security Official Docs](https://docs.spring.io/spring-security/reference/) — read "Authentication" section
- **Secondary:** [Baeldung — Spring Security](https://www.baeldung.com/security-spring) (entire series)
- **JWT Reference:** [jwt.io](https://jwt.io/) — decode and understand token structure
- **YouTube (exception to rule):** Java Brains — Spring Security series (good for visual flow understanding)

**Build after learning:** Complete auth service with JWT + refresh + OAuth2 Google login

---

### Topic 6: Testing

**Why it matters:** Companies increasingly reject candidates who can't test. A project with zero tests is a red flag. Testcontainers shows real maturity.

**Depth required:** Write unit + integration tests independently. Configure Testcontainers for real DB tests.

**Best Sources:**
- **Primary:** [JUnit 5 Docs](https://junit.org/junit5/docs/current/user-guide/)
- **Secondary:** [Baeldung — Testing](https://www.baeldung.com/spring-boot-testing)
- **Best written guide:** [reflectoring.io — Testing Spring Boot](https://reflectoring.io/spring-boot-test/)
- **Testcontainers:** [Testcontainers Official Docs](https://testcontainers.com/guides/testing-spring-boot-rest-api-using-testcontainers/)
- **Mockito:** [Mockito Official Docs](https://site.mockito.org/)

**Build after learning:** Full test suite for your auth service

---

### Topic 7: Microservices + Spring Cloud

**Why it matters:** Every product company above 10 LPA is running microservices. You must speak this language.

**Depth required:** Build a 3-service system. Explain Circuit Breaker, Service Discovery, API Gateway to an interviewer confidently.

**Best Sources:**
- **Primary:** [microservices.io](https://microservices.io/) — Chris Richardson's patterns catalog (free, authoritative)
- **Secondary:** [Baeldung — Spring Cloud](https://www.baeldung.com/spring-cloud-series)
- **Official Docs:** [Spring Cloud Docs](https://spring.io/projects/spring-cloud)
- **Resilience4j:** [Resilience4j Docs](https://resilience4j.readme.io/)
- **(Optional, paid):** Udemy — "Master Microservices with Spring Boot, Docker, Kubernetes" — Ranga Karanam

**Build after learning:** 3-service microservices app with discovery + gateway + circuit breaker

---

### Topic 8: Docker

**Why it matters:** "Works on my machine" doesn't get you hired. Every senior engineer is expected to containerize their own apps.

**Depth required:** Write Dockerfiles, docker-compose files. Debug container networking issues.

**Best Sources:**
- **Primary:** [Docker Official Docs — Getting Started](https://docs.docker.com/get-started/)
- **Secondary:** [Baeldung — Docker with Spring Boot](https://www.baeldung.com/dockerizing-spring-boot-application)
- **Multi-stage builds:** [Docker multi-stage docs](https://docs.docker.com/build/building/multi-stage/)

**Build after learning:** docker-compose.yml for full microservices stack

---

### Topic 9: Apache Kafka

**Why it matters:** Async event-driven architecture is standard at scale. Kafka is the de facto messaging system in India's product companies.

**Depth required:** Implement producer/consumer. Explain partitions, consumer groups, and offset management to interviewers.

**Best Sources:**
- **Primary:** [Kafka Official Docs](https://kafka.apache.org/documentation/)
- **Secondary:** [Baeldung — Spring Kafka](https://www.baeldung.com/spring-kafka)
- **Deep understanding:** [Confluent Kafka Fundamentals (free)](https://developer.confluent.io/learn-kafka/)
- **Official:** [Spring Kafka Docs](https://docs.spring.io/spring-kafka/reference/)

**Build after learning:** Event-driven order notification system

---

### Topic 10: Redis

**Why it matters:** Caching is performance. Interviewers ask "how do you scale this API to 1M requests?" — your first answer should involve caching strategy.

**Depth required:** Implement caching with Spring. Explain cache-aside pattern and TTL strategy.

**Best Sources:**
- **Primary:** [Redis Official Docs](https://redis.io/docs/)
- **Secondary:** [Baeldung — Spring Cache with Redis](https://www.baeldung.com/spring-boot-redis-cache)
- **Spring Cache:** [Spring Cache Docs](https://docs.spring.io/spring-framework/reference/integration/cache.html)

**Build after learning:** Cached product catalog + rate limiter + distributed lock

---

### Topic 11: Database Performance

**Why it matters:** Slow queries bring down production. Senior engineers are expected to find and fix them.

**Depth required:** Read EXPLAIN ANALYZE plans. Know when and what indexes to add.

**Best Sources:**
- **Primary:** [PostgreSQL Official Docs — Performance Tips](https://www.postgresql.org/docs/current/performance-tips.html)
- **Secondary:** [Use the Index, Luke](https://use-the-index-luke.com/) — best free resource for SQL indexing
- **HikariCP:** [HikariCP README](https://github.com/brettwooldridge/HikariCP)
- **Liquibase:** [Liquibase Official Docs](https://docs.liquibase.com/)

**Build after learning:** Performance-optimized order management schema with before/after benchmarks

---

### Topic 12: System Design

**Why it matters:** System design rounds exist at every company above 10 LPA. You will definitely face this.

**Depth required:** Design 5–6 systems confidently. Estimate scale. Know trade-offs.

**Best Sources:**
- **Primary:** [System Design Primer (GitHub)](https://github.com/donnemartin/system-design-primer) — free, comprehensive
- **Secondary:** [ByteByteGo Newsletter (Alex Xu)](https://blog.bytebytego.com/) — free tier has great content
- **Book (optional, paid):** "System Design Interview" — Alex Xu (Vol 1)
- **Practice:** [Excalidraw](https://excalidraw.com/) for diagramming

**Build after learning:** Document 6 system designs in your GitHub

---

## 7. PROJECT ROADMAP

### PROJECT 1: SmartStore — E-Commerce Backend API

**Build during:** Months 1–2 (evolves week by week)  
**What it demonstrates:** Core backend engineering skills

**Tech Stack:** Spring Boot 3.x + PostgreSQL + Redis + Spring Security + Docker + Spring Actuator

**Features to Build (in order):**

```
Phase 1 (Month 1):
  ├── User management (register, login, profile)
  ├── Product catalog (CRUD, categories, images metadata)
  ├── Search & filtering (Specifications API)
  ├── Pagination + sorting
  └── Admin dashboard endpoints

Phase 2 (Month 2):
  ├── JWT authentication + refresh tokens
  ├── Role-based access (ADMIN, CUSTOMER)
  ├── Cart management (Redis for session)
  ├── Order placement (transactional)
  ├── Order status lifecycle (PENDING → CONFIRMED → SHIPPED → DELIVERED)
  └── Full test suite (unit + integration + Testcontainers)
```

**What makes it impressive:**
- Testcontainers-backed integration tests
- Schema versioned with Liquibase
- API documented with SpringDoc/Swagger
- Docker + docker-compose setup
- CI/CD GitHub Actions pipeline
- Rate limiting on APIs
- ProblemDetail (RFC 7807) error responses

**README must include:**
- Architecture diagram
- API documentation link
- How to run locally (one command)
- Design decisions explained

---

### PROJECT 2: MicroCart — Microservices Order Management System

**Build during:** Months 2–3 (new project, bigger scope)  
**What it demonstrates:** Distributed systems, microservices, Kafka, Redis

**Tech Stack:** Spring Boot 3.x + Spring Cloud + Kafka + Redis + PostgreSQL + Docker Compose + Resilience4j

**Architecture:**

```
                    ┌──────────────────┐
                    │   API Gateway    │  (Spring Cloud Gateway)
                    │   Port: 8080     │
                    └────────┬─────────┘
                             │
           ┌─────────────────┼─────────────────┐
           │                 │                 │
    ┌──────┴──────┐  ┌───────┴──────┐  ┌──────┴──────┐
    │ User Service│  │Product Service│  │Order Service│
    │  Port: 8081 │  │  Port: 8082  │  │  Port: 8083 │
    └──────┬──────┘  └───────┬──────┘  └──────┬──────┘
           │                 │                 │
      PostgreSQL         PostgreSQL        PostgreSQL
      (users_db)         (products_db)     (orders_db)
                                                │
                                            Kafka (Events)
                                                │
                                    ┌───────────┴──────────┐
                                    │  Notification Service │
                                    │     Port: 8084        │
                                    └──────────────────────┘
```

**Services:**

| Service | Responsibilities |
|---------|-----------------|
| `user-service` | Registration, login, JWT issuance, profile |
| `product-service` | Product catalog, inventory management, Redis caching |
| `order-service` | Order placement, status updates, publishes Kafka events |
| `notification-service` | Consumes Kafka events, logs/sends notifications |
| `api-gateway` | Routing, JWT validation, rate limiting |

**Key implementation highlights:**
- Circuit breaker: order-service → product-service (Resilience4j)
- Kafka: `OrderCreatedEvent`, `OrderStatusChangedEvent`
- Redis: Product cache, inventory lock (distributed lock)
- Service discovery: Eureka
- Distributed tracing: Micrometer + Zipkin
- Full docker-compose (boots entire stack)
- GitHub Actions CI pipeline

**README must include:**
- Full architecture diagram (Excalidraw or draw.io)
- API contract for each service
- How to start: `docker-compose up`
- Kafka topic design
- Design decisions (ADRs)

---

## 8. INTERVIEW-FOCUSED BACKEND TOPICS

### Category 1: Spring Boot Internals (High Frequency)

1. How does Spring Boot auto-configuration work? How would you disable specific auto-config?
2. Explain Spring bean lifecycle from instantiation to destruction
3. What is the difference between `@Component`, `@Service`, `@Repository`?
4. How does `@Transactional` work internally? (Proxy-based AOP)
5. What is the difference between `@Bean` and `@Component`?
6. Explain `@Conditional` annotations and when you'd create a custom one
7. How would you create a custom Spring Boot Starter?
8. What is the ApplicationContext vs BeanFactory?
9. What are bean scopes? When would you use Prototype?
10. How does Spring handle circular dependencies? How would you fix one?

### Category 2: JPA/Hibernate (High Frequency)

1. What is the N+1 problem? How do you detect and fix it?
2. Explain the difference between `@OneToMany(fetch = LAZY)` and `EAGER`
3. What is the first-level cache vs second-level cache in Hibernate?
4. How does `@Transactional` propagation work? Explain `REQUIRED` vs `REQUIRES_NEW`
5. What is optimistic locking? How do you implement it with `@Version`?
6. When would you use native queries vs JPQL vs Specifications?
7. What is a dirty check in Hibernate? How does it work?
8. Explain the difference between `merge()` and `persist()`
9. What are the problems with `CascadeType.ALL` + `orphanRemoval`?
10. How do you implement soft delete in JPA?

### Category 3: Spring Security + Auth

1. How does Spring Security filter chain work?
2. Explain JWT structure and validation process
3. How do you implement refresh token rotation securely?
4. What is the difference between authentication and authorization?
5. How does OAuth2 authorization code flow work?
6. How would you implement method-level security?
7. How do you prevent CSRF attacks? When is CSRF not needed?
8. What is the difference between symmetric and asymmetric JWT signing?
9. How would you invalidate a JWT before its expiry?
10. How do you implement RBAC with permission-based access?

### Category 4: Microservices + Distributed Systems

1. What is the CAP theorem? Give a practical example of CP vs AP choice
2. How does a Circuit Breaker work? What are the states?
3. How do you handle distributed transactions (Saga pattern)?
4. What is eventual consistency? How do you handle it in your code?
5. How does service discovery work with Eureka?
6. What is an API Gateway? What responsibilities does it own?
7. Explain the difference between synchronous and asynchronous communication
8. How do you handle data consistency across microservices?
9. What is idempotency? How do you implement idempotent APIs?
10. How would you handle a failure in one service in a chain of 4 services?

### Category 5: Kafka

1. What is the difference between a topic, partition, and offset?
2. How does Kafka guarantee message ordering?
3. What is a consumer group? How does partition assignment work?
4. Explain at-least-once vs exactly-once delivery semantics
5. What is a Dead Letter Topic? When would you use it?
6. How do you handle schema evolution in Kafka messages?
7. What is consumer lag and why does it matter?
8. How does Kafka differ from RabbitMQ? When would you choose each?

### Category 6: Redis + Caching

1. What caching patterns do you know? Explain cache-aside
2. How do you handle cache invalidation?
3. What is a cache stampede? How do you prevent it?
4. How do you implement distributed locking with Redis?
5. What is the difference between Redis Pub/Sub and Kafka?
6. What Redis eviction policies do you know? When to use LRU vs LFU?

### Category 7: Database Performance

1. How do B-Tree indexes work?
2. When would a query NOT use an index?
3. How do you read a PostgreSQL EXPLAIN ANALYZE output?
4. What is the difference between a clustered and non-clustered index?
5. When would you use a partial index?
6. How does HikariCP connection pool work? What settings would you tune?
7. What is a database deadlock? How do you detect and prevent it?

### Category 8: System Design (Be ready to whiteboard)

**Common questions at 15–20 LPA:**
- Design an e-commerce order management system
- Design a rate limiter
- Design a URL shortener
- Design a notification service
- Design a payment processing system (idempotency focus)

**Framework for answering:**
1. Clarify requirements (2 min)
2. Estimate scale (RPS, storage, bandwidth) (2 min)
3. High-level architecture (5 min)
4. Deep dive on 2 components interviewer picks (10 min)
5. Identify bottlenecks + trade-offs (3 min)

---

## 9. TRACKER TEMPLATE

**Copy this table into Notion, Google Sheets, or Excel:**

### Weekly Learning Tracker

| Week | Topic | Status | Hours Spent | Concepts Done | Code Built | Tests Written | Committed? | Blocker |
|------|-------|--------|-------------|---------------|------------|---------------|------------|---------|
| 1 | Spring Boot Internals | 🟡 In Progress | 8 | Bean Lifecycle, Auto-config | Custom Starter | No | Yes | - |
| 2 | JPA/Hibernate Advanced | ⬜ Not Started | 0 | - | - | - | No | - |
| ... | ... | ... | ... | ... | ... | ... | ... | ... |

**Status Legend:** ⬜ Not Started | 🟡 In Progress | ✅ Done | ❌ Skipped

---

### Project Tracker

| Project | Feature | Status | Start Date | End Date | Notes |
|---------|---------|--------|-----------|---------|-------|
| SmartStore | User Auth (JWT) | ✅ Done | Day 1 | Day 3 | - |
| SmartStore | Product CRUD | 🟡 In Progress | Day 4 | - | N+1 bug to fix |
| MicroCart | API Gateway setup | ⬜ Not Started | - | - | - |

---

### Interview Preparation Tracker

| Topic Category | Questions Reviewed | Mock Answered | Confidence (1-5) | Last Reviewed |
|---------------|-------------------|---------------|-----------------|---------------|
| Spring Internals | 10 | 7 | 4 | Week 4 |
| JPA/Hibernate | 0 | 0 | 2 | - |
| Microservices | 0 | 0 | 1 | - |

---

### Job Application Tracker

| Company | Role | Applied Date | Source | Status | Interview Round | Notes |
|---------|------|-------------|--------|--------|----------------|-------|
| Razorpay | SDE-2 Backend | Month 4 Week 1 | LinkedIn | Applied | - | - |

---

### GitHub Daily Commit Tracker

```
Month 1: ✅✅✅✅✅✅✅✅✅✅✅✅✅✅✅✅✅✅✅✅✅✅✅✅✅✅✅✅✅✅
Month 2: ✅✅✅⬜✅✅✅✅✅✅✅✅✅✅✅✅✅✅✅✅✅✅✅✅✅✅✅✅✅⬜
Month 3: [fill as you go]
Month 4: [fill as you go]
```

---

## 10. WEEKLY REVIEW SYSTEM

**Every Sunday evening, spend 30 minutes answering these questions:**

### Technical Review (15 min)

1. What did I learn this week? (list 5 specific things)
2. What did I build? (describe in 2 sentences)
3. What confused me most? (write it down — this is your weak spot)
4. Can I explain this week's topic to a junior without notes? (test yourself)
5. Did I hit this week's deliverable/GitHub commit?

### Progress Check (10 min)

6. Am I on schedule with the roadmap? (yes/no + how far off)
7. How many hours did I actually study vs planned?
8. Are my projects progressing? What's the next feature?
9. Did I write any tests this week? (if not, fix that first next week)

### Week Ahead (5 min)

10. What is the one thing I must accomplish next week?
11. What will I build (specific feature, not vague)?
12. What resource will I read (specific article or docs page)?

---

### Monthly Milestone Checkpoints

**End of Month 1 — you are ready if:**
- [ ] You can explain Spring auto-configuration without notes
- [ ] You can fix an N+1 bug given a codebase to review
- [ ] SmartStore Phase 1 is live on GitHub
- [ ] You've written at least 20 unit tests
- [ ] You can design a REST API from scratch correctly

**End of Month 2 — you are ready if:**
- [ ] You can build a JWT auth system from scratch
- [ ] You have >75% test coverage on SmartStore
- [ ] MicroCart has 3 services running via docker-compose
- [ ] You can explain Circuit Breaker to an interviewer
- [ ] You understand how Spring Security filter chain works

**End of Month 3 — you are ready if:**
- [ ] You have Kafka events flowing in MicroCart
- [ ] Redis caching is live in SmartStore with cache eviction working
- [ ] You can read a PostgreSQL EXPLAIN ANALYZE plan
- [ ] You've documented 5 system designs in your GitHub
- [ ] You can estimate RPS/storage for a system design question

**End of Month 4 — you are ready if:**
- [ ] Both projects are fully polished on GitHub with READMEs
- [ ] GitHub Actions CI pipeline is green
- [ ] Grafana dashboard shows your app metrics
- [ ] You've done 20+ mock interview questions out loud
- [ ] You've submitted 40+ job applications
- [ ] Your LinkedIn is updated and complete

---

## 11. FINAL 4-MONTH SUCCESS CHECKLIST

### Skills ✅

- [ ] Spring Boot auto-configuration explained without notes
- [ ] Bean lifecycle hooks implemented in code
- [ ] N+1 problem solved using JOIN FETCH and EntityGraph
- [ ] JPA Specifications API for dynamic queries
- [ ] Optimistic locking implemented
- [ ] REST API with ProblemDetail error format
- [ ] API versioning implemented
- [ ] JWT auth + refresh token rotation
- [ ] OAuth2 Google login working
- [ ] Role-based + method-level security
- [ ] 75%+ test coverage on at least one service
- [ ] Testcontainers integration tests
- [ ] 3-service microservices app running
- [ ] Circuit breaker with Resilience4j
- [ ] Kafka producer + consumer + DLT
- [ ] Redis caching with eviction strategy
- [ ] Distributed lock with Redis
- [ ] PostgreSQL index optimization (before/after measured)
- [ ] Liquibase migration scripts
- [ ] Docker multi-stage build
- [ ] docker-compose for full stack
- [ ] GitHub Actions CI pipeline
- [ ] Spring Actuator + Prometheus + Grafana
- [ ] 6 systems designed and documented

### Projects ✅

- [ ] SmartStore: public GitHub, Swagger docs, Testcontainers tests, docker-compose, CI pipeline
- [ ] MicroCart: public GitHub, architecture diagram, Kafka, Redis, Resilience4j, docker-compose
- [ ] Both projects have 200+ word README with how-to-run

### Portfolio ✅

- [ ] GitHub profile README complete
- [ ] 2 projects pinned
- [ ] System design notes repo pinned
- [ ] LinkedIn updated with projects + skills
- [ ] Clean code examples visible in code

### Interview Readiness ✅

- [ ] All 8 categories of interview questions reviewed
- [ ] 20+ mock system design sessions done (self or peer)
- [ ] Can whiteboard any of the 6 system designs
- [ ] Can explain both projects in 5 minutes each
- [ ] STAR stories ready for 5 behavioral questions

### Job Search ✅

- [ ] 100+ applications submitted by end of Month 4
- [ ] Referrals sought at 10+ target companies
- [ ] Application tracker maintained throughout

---

## 🔖 QUICK REFERENCE: BEST RESOURCES SUMMARY

| Topic | Best Free Resource |
|-------|-------------------|
| Spring Boot | docs.spring.io + baeldung.com |
| JPA/Hibernate | thorben-janssen.com |
| REST API Design | Microsoft Azure Docs + reflectoring.io |
| Design Patterns | refactoring.guru |
| Spring Security | Spring Security official docs + Baeldung |
| Testing | reflectoring.io Spring Boot Testing |
| Microservices | microservices.io (Chris Richardson) |
| Docker | docs.docker.com |
| Kafka | Confluent Developer (developer.confluent.io) |
| Redis | redis.io/docs |
| DB Performance | use-the-index-luke.com |
| System Design | github.com/donnemartin/system-design-primer |
| System Design Blog | blog.bytebytego.com (free tier) |

---

*Last updated: Month 0 | Next review: End of Week 1*

> **Remember:** The goal is not to read everything. The goal is to build something every week and become someone who solves real engineering problems. The reading is just preparation for the building. Ship code. Commit daily. Review weekly.
