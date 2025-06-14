System Design

Server <-> End user

# Horizontal scaling Vs Vertical Scaling

1. Horizontal scaling:
Buy more machines
requires load balancer
resilient - if one machine goes down, service is not interrupted
network calls - RPC (Slow)
data consistency will be difficult
scales well 


2. Vertical scalinng:
Buy big machine
does not require load balancer
not resilient - single point of failure
inter process communication
data consistent
hardware limit

# Start with building a system:

1. optimise process and increase throughput using the same resource - max utilisation (Vertical scaling)
2. run process during non peak hours - preprocessing and cron jobs
3. backup and avoid single point of failure - Backup
4. buy more resources - Horizontal scaling


# Microservice architecture 

# Distributed system - (Partitions)

# Load Balancer

# Decoupling - (Extensible)

# Logging and metrics 

# High Level and Low level Design: 

High level is system design
low level is coding

# Consistent Hashing:

If there are N-servers and M-End users, We need to distribute it equally to all the servers

hash function f() = M % N (M modulo N) which gives reminder as the result 

suppose 10 servers and 100 users...then user request will be given to the server based on the hash function. Ideal case, each server will handle 10 users. 

But in this case, suppose we are adding a new server, then each server will lose around 1 user. In real world, not always different user logs in, if suppose 1 user logs in 20 times, then it is better to cache the result. but while adding the server, the hash result changes and the result will be fetched from another server and cache becomes useless. also the delay would be signifant

# CDN - Content Delviery Network

# Caching

L1, L2 and L3 CPU cache

# IP / TCP 

# DNS - Domain Name Service

DNS Registrar

# Application Layer protocol - https://

# Client/Server model

# Rest API - Application Programming Interface
JSON

Request 
Response

# GraphQl
gRPC - Protocol buffers - serialized into binary, lot faster than RestApi

# Web Sockets - Take an example of Messaging apps

if we use http, we need to keep on polling the senders for any new messages. but in case of websockets, it supports bidirectional communication

Database - For more efficient storage and retrival 

# SQL

# B-Tree datastructure 

# ACID compliance 
A - All or nothing
C - Consistency - relationship across multiple tables 
I - No two transaction interfere with each other 
D - Durability - Even if system restarts, the data will be there


# NoSql

No relations
Sharding for horizontal scaling 
replication for redundancy 
leader and follower
CAP theorem 

# Message queues 

Common practices:

- Index DBs to optimize reads
- Shard SQL for horizontal scaling
- Auto-scale to handle traffic spikes
- Use CDNs to reduce global latency
- No perfect solution—only trade-offs
- Assume failures—build fault tolerance
- Async processing for non-urgent tasks
- Write-through cache for write-heavy apps
- Heartbeats & health checks detect failures
- Circuit breakers prevent cascading failures
- Denormalize DBs for read-heavy workloads
- Prefer microservices over monoliths for scale
- Read-through cache boosts read-heavy apps
- Event-driven architecture decouples components
- Avoid over-engineering—add features when needed
- Use API versioning to manage backward compatibility
- Optimize database queries to avoid N+1 query problems
- Use distributed tracing for monitoring and debugging microservices
- Apply schema evolution strategies to handle DB migrations smoothly
- Leverage gRPC for efficient, high-performance service communication
- Implement database connection pooling to optimize resource usage
- Monitor and log everything—observability is key for debugging
- Design for eventual consistency in distributed systems
- Define functional & non-functional requirements first
- Replication & redundancy enhance fault tolerance
- Use feature flags for safe and controlled rollouts
- Rate limiting prevents overload & DoS attacks
- Websockets enable real-time communication
- SQL for structured data & ACID compliance
- Message queues enable async processing
- Load balancers improve traffic distribution
- Partition & shard data for large datasets
- Data lakes & warehouses for analytics
- API gateways simplify microservices
- Prefer horizontal scaling for growth
- Blob storage is best for media files
- Idempotency simplifies retry logic
- NoSQL suits unstructured data
- Design clear, secure APIs

