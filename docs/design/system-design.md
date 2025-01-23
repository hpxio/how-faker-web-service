# System Design Considerations

## Requirements and Constraints

### Functional Requirements
- **Custom Format:** Should allow users to specify sturcture (e.g., fields, data types, range, length).
- **Bulk Data:** Generate large volumes of fake data (bulk generation).
- **Multi Format:** Support multiple output formats: JSON, SQL, CSV, etc.
- **Easy Usage:** Provide an API to handle user requests for data generation.

### Non-Functional Requirements
- **Scalability:** Handle multiple concurrent user requests and large datasets efficiently.
- **Performance:** Generate data quickly without bottlenecks.
- **Extensibility:** Easily add support for new data formats or new field types.
- **Fault tolerance and reliability:** Ensure the service can recover from failures.
- **Cost-effectiveness:** Optimize resource usage during data generation.

### Assumptions:
- Users will specify data generation requirements via a REST API.
- Generated datasets could range from a few KBs to several MBs.
- Initially there will limit on amount of data generated.
- We assume eventual consistency is acceptable in non-critical scenarios.

## High-Level Architecture
At a high level, the system consists of the following components:

- **API Gateway**
  - Provides an interface for users to define schemas, request data generation, and download results
  - Handles authentication and authorization via user-authentication & session token.
- **Data Generation Service**
  - Core service that parses user specifications and generates fake data based on those schemas.
  - Supports modular plugins for different data types and output formats.
- **Job Queue/Task Processor**
  - Handles bulk data generation asynchronously to prevent long-running requests from blocking resources.
- **Monitoring and Logging**
  - Tracks performance metrics, errors, and usage statistics.
- **Database**
  - Stores user stats and request metadata for reporting & stats.
  - Keeps logs of completed jobs and metadata for the generated datasets.

### High-Level Flow
```text
 User → [API Gateway] → [Job Queue] → 	[Task Processor]
                                        	↓
					[Data Generation Service]
						↓
                          		[Stats Service]
                  
```

#### Component Breakdown
- **API Gateway**
  - **Purpose:**
    Handles incoming user requests, including schema definitions, format preferences, and data generation requests.
  - **Implementation:**
    - Expose RESTful APIs (e.g., POST /generate-data, POST /add-user, GET /user-stats).
    - Imposer Security by verifying user credentials and session tokens.
    - Validate user inputs (e.g., valid schema definition, output format).
    - Throttle requests to prevent abuse.
  - **Tech Stack:**
    - Frameworks: Spring Cloud Gateway
    - Authentication: OAuth2 or JWT for User Authentication.

- **Data Generation Service**
  - **Purpose:**
      The core service responsible for creating data based on user schemas and serializing it into the required formats.
  - **Details:**
    - The schema is parsed and converted into an intermediate representation.
    - Each field type (e.g., string, integer, date) is mapped to a faker module.
    - Data is streamed (rather than generated all at once) to handle large datasets efficiently.[Option-1]
    - Data can be sent as paginated response to avoid long wait-time or queuing. [Option-2]
    - Support for different output formats (JSON, XML, SQL, CSV) via serializers.
  - **Tech Stack:**
    - Language: Java, with Faker built from scratch (for learning)

- **Job Queue / Task Processor**
  - **Purpose:**
    Decouple the data generation process from the user request to handle long-running or heavy jobs asynchronously.
  - **Details:**
    - User requests are enqueued in a distributed message broker (e.g., RabbitMQ or Kafka).
    - _Workers consume jobs, process the data generation task, and store the result in file storage._ ‼️
    - Supports retry logic for failed jobs and ensures fault tolerance.
  - **Tech Stack:**
    - Queue: RabbitMQ or Kafka.
    - Task Processing: Spring Boot Services, Custom Threads

- **Database**
  - **Purpose:**
    Store metadata about jobs, schema definitions, and user stats.
  - **Schema:**
    - Users Table: Store user details, consumption stats, etc.
    - Request Metadata: Store frequency of data types, formats, etc.
    - Jobs Table: Track status (e.g., pending, processing, completed).
  - **Tech Stack:**
    - SQL Database: MySQL for User Data.
    - Alternatives: NoSQL (MongoDB, DynamoDB) for Request Metadata & Job Status.

- **Monitoring and Logging**
  - **Purpose:**
    Observe system performance and quickly identify bottlenecks or failures.
  - **Implementation:**
    - Centralized logging for API requests and task processing using ELK Stack
    - Metrics collection (e.g., latency, throughput) using Prometheus/Grafana.


### Scalability Considerations
- **Horizontal Scaling**
  - `API Gateway`: Use a load balancer to distribute requests across multiple instances.
  - `Task Processors`: Scale the workers dynamically based on queue length.
- **Data Streaming**‼️
  - Generate and stream large datasets directly to storage to reduce memory usage.
- **Sharding**
  - For extremely large schemas or datasets, split data generation tasks into smaller chunks and process them in parallel.
- **Caching**
  - Cache commonly requested data patterns or small datasets to reduce computation time.
- **Rate Limiting**
  - Throttle API requests to prevent abuse by heavy users.

### Challenges and Mitigations
- Memory Consumption: Stream data generation to storage instead of keeping it in memory.
- Schema Complexity: Validate user-provided schemas thoroughly to prevent runtime errors.
- Format-Specific Challenges: Abstract format generation into modular plugins to handle future formats.


## Low Level Architecture
The high-level components from the HLD will be translated into Spring Boot components:
- Controller Layer: API endpoints for receiving user requests.
- Service Layer: Business logic for schema validation and data generation.
- Task Queue: Asynchronous job management.
- Worker: Processes jobs from the queue.
- File Storage Service: Handles storage and retrieval of generated files.
- Database Layer: Stores job metadata and schema details.

_TBD_
