# Database Development Best Practices with Augment Code

## Overview

This guide provides comprehensive best practices for using Augment Code effectively when working with databases, including SQL and NoSQL systems, schema design, migrations, performance optimization, and ORM integration.

## 1. Structuring Requests for Database Development

### Database-Specific Request Structure
- **Database System**: PostgreSQL, MySQL, MongoDB, Redis, Elasticsearch, etc.
- **Scale Context**: Data volume, query patterns, concurrent users, performance requirements
- **Architecture**: Single instance, replication, sharding, clustering, cloud-managed
- **Application Integration**: ORM/ODM, connection pooling, caching strategies
- **Performance Goals**: Query response times, throughput, availability targets

### Well-Structured Database Request Examples

#### Query Performance Optimization
```
I need to optimize slow queries in my PostgreSQL database for an e-commerce application. The products table has 2 million records, and the search query that filters by category, price range, and availability is taking 3-5 seconds. Current query uses multiple JOINs with orders and inventory tables. Using PostgreSQL 14 with 16GB RAM, need to reduce query time to under 500ms.
```

#### Schema Design and Migration
```
I'm designing a database schema for a multi-tenant SaaS application using PostgreSQL. Need to support 1000+ tenants with isolated data, user management, subscription billing, and audit logging. Considering row-level security vs separate schemas vs separate databases. Application uses Node.js with Prisma ORM and needs to handle 10,000+ concurrent users.
```

#### NoSQL Data Modeling
```
I need to migrate from a relational database to MongoDB for a social media application. Current PostgreSQL schema has complex relationships between users, posts, comments, and likes. Need to design document structure for efficient queries, handle denormalization, and maintain data consistency. Application serves 100K+ users with real-time features.
```

#### Database Scaling Strategy
```
My MySQL database is hitting performance limits with 50GB of data and 1000+ concurrent connections. Experiencing slow queries, connection pool exhaustion, and replication lag. Need to implement read replicas, connection pooling optimization, and possibly sharding strategy. Application is a high-traffic web platform with strict uptime requirements.
```

## 2. Database Development Tasks Augment Code Excels At

### Core Database Strengths
- **Schema Design**: Normalization, denormalization, indexing strategies, constraint design
- **Query Optimization**: Performance tuning, execution plan analysis, index optimization
- **Migration Management**: Schema changes, data migrations, version control, rollback strategies
- **Performance Tuning**: Connection pooling, caching, replication, partitioning
- **Data Modeling**: Relational design, NoSQL document structure, graph relationships
- **Security**: Access controls, encryption, audit logging, compliance requirements

### Database System Expertise

#### Relational Databases
- **PostgreSQL**: Advanced features, JSON support, full-text search, extensions
- **MySQL**: InnoDB optimization, replication, partitioning, performance tuning
- **SQL Server**: T-SQL optimization, indexing, Always On, performance monitoring
- **Oracle**: PL/SQL, partitioning, RAC, performance tuning, enterprise features

#### NoSQL Databases
- **MongoDB**: Document modeling, aggregation pipelines, sharding, replica sets
- **Redis**: Caching strategies, data structures, clustering, persistence
- **Elasticsearch**: Search optimization, mapping design, cluster management
- **Cassandra**: Wide-column modeling, consistency levels, cluster design

#### Cloud Database Services
- **AWS**: RDS, Aurora, DynamoDB, DocumentDB, ElastiCache
- **Azure**: SQL Database, Cosmos DB, Cache for Redis
- **GCP**: Cloud SQL, Firestore, BigQuery, Memorystore

### ORM and Database Integration
- **Prisma**: Schema definition, migrations, type safety, query optimization
- **TypeORM**: Entity design, migrations, query builder, performance
- **Sequelize**: Model definitions, associations, transactions, pooling
- **Mongoose**: Schema design, middleware, population, aggregation
- **SQLAlchemy**: ORM patterns, query optimization, session management
- **Entity Framework**: Code-first, migrations, LINQ optimization

## 3. Providing Database Development Context

### Essential Database Context Elements
- **Database System**: "PostgreSQL 14 with 32GB RAM, SSD storage"
- **Data Scale**: "5 million users, 50GB data, 10K queries/second peak"
- **Schema Complexity**: "50 tables with complex relationships, heavy JOINs"
- **Performance Requirements**: "Sub-100ms query response, 99.9% uptime"
- **Integration**: "Node.js with Prisma ORM, Redis for caching"

### Database-Specific Context Examples

#### Good vs Better Context
```
Good: "The query is slow"
Better: "The user search query on PostgreSQL is taking 2-3 seconds. Query searches users table (1M records) with filters on name, email, and status, joins with profiles table for additional data. Using ILIKE for text search, no current indexes on search columns. Need sub-500ms response time."

Good: "Need to design a schema"
Better: "Need to design PostgreSQL schema for a project management SaaS with multi-tenancy. Requirements: users, projects, tasks, comments, file attachments, time tracking, and reporting. Expecting 10K+ users per tenant, 100+ tenants. Need row-level security and efficient queries for dashboard views."

Good: "Database migration failing"
Better: "Prisma migration failing when adding NOT NULL constraint to existing table with 2M records. Migration times out after 30 minutes on PostgreSQL 13. Need to add column with default value and backfill data without downtime. Table has active read/write operations during business hours."
```

### Schema Context
```sql
-- Current table structure
CREATE TABLE products (
    id SERIAL PRIMARY KEY,
    name VARCHAR(255) NOT NULL,
    category_id INTEGER REFERENCES categories(id),
    price DECIMAL(10,2),
    created_at TIMESTAMP DEFAULT NOW()
);

-- Current indexes
CREATE INDEX idx_products_category ON products(category_id);
CREATE INDEX idx_products_price ON products(price);
```

## 4. Leveraging Codebase Retrieval for Database Projects

### Database-Specific Retrieval Patterns
- "Show me all database queries and their performance characteristics"
- "Find all database schema definitions and migration files"
- "How are database connections and transactions managed?"
- "Where are we implementing caching and what's the cache strategy?"
- "Show me the current ORM models and their relationships"

### Schema Understanding Queries
- "Help me understand the current database schema and relationships"
- "How are we handling data validation and constraints?"
- "Where are we implementing database indexes and optimization?"
- "Show me how database migrations are structured and managed"
- "How are we handling database seeding and test data?"

### Performance Analysis Queries
- "Find queries that might be causing performance bottlenecks"
- "Show me where we're doing N+1 queries or inefficient data loading"
- "Where are we implementing database connection pooling?"
- "How are we handling database transactions and concurrency?"

## 5. Iterating on Database Solutions

### Database Development Iteration Process
1. **Analyze**: "Help me understand why this query is performing poorly"
2. **Plan**: "What's the best approach to implement this data model?"
3. **Implement**: Start with schema design, then optimization, then scaling
4. **Test**: "Help me create performance tests for these database operations"
5. **Optimize**: Address query performance, indexing, and connection management
6. **Review**: "Review this schema design for best practices and scalability"

### Common Database Iteration Scenarios

#### Performance Issues
- Share query execution plans and timing analysis
- Provide database monitoring metrics and slow query logs
- Include connection pool statistics and resource utilization
- Mention specific queries or operations causing bottlenecks

#### Schema Design Challenges
- Describe data relationships and access patterns
- Include business requirements and query patterns
- Share current schema structure and constraints
- Provide details about data volume and growth projections

#### Migration Problems
- Describe current schema state and desired changes
- Include migration scripts and error messages
- Share details about data volume and downtime constraints
- Provide information about application dependencies

#### Scaling Concerns
- Describe current traffic patterns and growth projections
- Include database metrics and resource utilization
- Share details about read/write patterns and hotspots
- Provide information about availability and consistency requirements

## 6. Database Development Communication Patterns

### Effective Database Question Patterns

#### For Schema Design
- "How should I design this database schema for optimal performance?"
- "What's the best way to handle this many-to-many relationship?"
- "How should I implement multi-tenancy in this database design?"
- "What's the optimal indexing strategy for these query patterns?"

#### For Performance Optimization
- "This query is slow - how can I optimize it?"
- "How can I improve the performance of this database operation?"
- "What's the best way to handle this large dataset efficiently?"
- "How should I implement caching for this data access pattern?"

#### For Migration and Maintenance
- "How should I structure this database migration safely?"
- "What's the best way to migrate this data without downtime?"
- "How can I implement proper backup and recovery procedures?"
- "How should I handle schema versioning and rollbacks?"

#### For Scaling and Architecture
- "How should I scale this database for increased load?"
- "What's the best approach for implementing read replicas?"
- "How can I implement effective database monitoring and alerting?"
- "How should I handle database clustering and high availability?"

### Database Communication Tips
- Use appropriate terminology for your database system
- Reference specific versions and configurations when relevant
- Mention performance requirements and scalability targets
- Include relevant schema and query context
- Specify consistency and availability requirements

## 7. Advanced Database Development Tips

### Leverage Database Expertise
- Ask about database-specific optimization techniques and patterns
- Get guidance on schema design and normalization strategies
- Request performance reviews focusing on query optimization
- Seek advice on backup, recovery, and disaster planning

### Modern Database Practices
- Stay updated on latest database features and capabilities
- Get guidance on cloud database services and managed solutions
- Learn about modern data modeling and architecture patterns
- Understand database security and compliance best practices

### Production Database Management
- Learn about proper monitoring and alerting strategies
- Understand capacity planning and performance tuning
- Get guidance on backup and disaster recovery procedures
- Implement proper security and access control measures

### Example Database Development Interaction Flow
```
You: "My PostgreSQL queries are getting slower as our user base grows, especially the dashboard queries."

Me: [Analyzes database schema] "I can see you're doing multiple JOINs across large tables without proper indexing. Let me examine your query patterns and current index strategy..."

You: "Yes, and we're also seeing connection pool exhaustion during peak hours."

Me: [Provides optimization plan] "Here's a comprehensive approach: implement composite indexes for your query patterns, optimize the JOIN order, add connection pooling configuration, and consider read replicas for dashboard queries..."

You: "That sounds good, but I'm also concerned about maintaining data consistency during high concurrency."

Me: [Addresses concurrency concerns] "Let me show you how to implement proper transaction isolation levels, add optimistic locking where appropriate, and design queries to minimize lock contention..."
```

---

*This guide provides database development-specific best practices for maximizing productivity with Augment Code. Keep it handy when working on database projects for optimal development workflows.*
