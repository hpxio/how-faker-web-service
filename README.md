# Faker Web Service

> Hands-on-With Faker Web Service, which enables client to generate data of specific structure in bulk.

## Objective

Faker Web Service (FakerWS) is aimed to generate structured data in bulk. It dynamically produces data on the fly based on user-defined specifications, offering flexibility and precision for diverse data generation needs. All APIs are inherently stateless, ensuring a scalable and efficient design.

### Key Objectives:
1. **System Design Exploration:**  
The primary purpose of FakerWS is to serve as a practical implementation for exploring and understanding the system design principles of services that handle large-scale data generation and transmission over the web.
2. **Hands-On Learning:**  
By developing this service, the focus is on gaining hands-on experience with various architectural decisions, understanding trade-offs, and tackling real-world challenges in both functional and non-functional domains.

### Learning Opportunities

FakerWS provides significant opportunities to address a wide range of challenges, including but not limited to:

**Non-Functional Challenges:**  
* Resource Optimization: Efficiently utilizing compute and memory resources for high performance.
* Scalability & Load Balancing: Designing a system capable of handling high concurrency and distributing load effectively.
* Security: Ensuring secure data handling, transmission, and API access.
* Validation & Monitoring: Managing robust input validations and implementing monitoring mechanisms for reliability.

**Functional Challenges:**  
* Data Consistency: Producing consistent results even under varying load conditions.
* Request-Response Management: Properly handling request formats, managing response structures, and ensuring smooth communication.
* Metadata Management: Dealing with HTTP headers and other metadata markers for better customization, debugging, and control of data flow.

### Impact

FakerWS is more than just a data generation tool — it is a platform for learning and refining core principles of distributed systems, API design, and scalable architecture. It serves as a sandbox for tackling real-world challenges in a controlled environment, offering deep insights into building robust and efficient web services.

## Expectations

By working with FakerWS, you are expected to learn and explore the following key areas:
1. **Design Patterns and Principles**  
   Understanding key patterns (e.g., Factory, Singleton, Builder) and principles like SOLID and DRY for scalable design.
1. **Memory Management and Optimization**  
   Learning about garbage collection, heap usage, object pooling, and frameworks like Ehcache or Caffeine for caching.
1. **Multithreading and Concurrency**  
   Exploring synchronization, thread pooling, and concurrent collections using Java Concurrency Framework or RxJava.
1. **Data Manipulation and String Handling**  
   Techniques for efficiently managing and processing large datasets and strings with libraries like Apache Commons or Guava.
1. **Scaling and Traffic Management**  
   Handling scalability challenges with load balancing using tools like NGINX or HAProxy and autoscaling strategies with Kubernetes.
1. **Resource Utilization and Optimization**  
   Monitoring resource usage (CPU, memory) and tuning performance using tools like JProfiler or VisualVM.
1. **Validations and Exception Handling**  
   Implementing robust data validation and error-handling mechanisms using frameworks like Hibernate Validator.
1. **Authentication, Security, and Monitoring**  
   Securing APIs with OAuth 2.0, JWT, and enabling observability with tools like Prometheus, Grafana, or ELK Stack.
1. **Data-Store Management**  
   Optimizing interactions with databases (SQL and NoSQL) using JPA/Hibernate, MongoDB, or Redis.
1. **Decentralized Truth Store**  
   Exploring distributed systems and eventual consistency using Apache Kafka, Cassandra, or Zookeeper.

## Scopes

The application is capable of generating following types of structured data:

* JSON Payload
* CSV Data
* SQL Statements

### Faker Data Types

The application supports creating following base-types:
* Date
* Time
* Timestamp
* First Name
* Last Name
* Middle Name
* City
* State
* Country
* Continent
* Address
* Pin Code
* Telephone Number
* Mobile Numnber
* UUID/GUID
* Month
* Week Days
* Calendar Year
* Season
* Number
* Decimal
* Binary
* Octal
* Hexadecimal
* Currency
* Amount
* Color
* Product Name
* Company Name
* Department Name
* Username
* Password
* Email
* Domain Name
* Website URL
* Debit/Credit Card Number
* Account Number
* Bank Name
* File Name
* File Path

The application also support creating data using custom-types. More details will be added soon.
* Random Alpha-Numeric
* Formatted Alpha-Numeric
* Base62 Encoded
* Base64 Encoded
* Custom Function

#### Multi-Format Support

* Date: ISO Date & Custom `DDMMYYY` Formats, Date Number, Date Between Range
* Time: ISO Time & Custom `HHMMSS` Formats, Only HH, MM or SS, Time Between Range
* Timestamp: ISO Timestamp, Epoch Time, Timezone Based, Composite Formats (Date+Time+TZ)
* Number: Short Number, Long Number, Signed Numbers, Unsigned Numbers, Numbers Between Range
* Decimal: Pie Value, Precision Digits Format, TBD*, Decimals Between Range
* City: Random, State Specific, Country Specific, Starting Letter Specific
* State: Random, Country Specific, Starting Letter Specific
* Country: Random, Continent Specific, Starting Letter Specific
* Address*: Random, Country Specific*, City Specific*
* Telephone Number: 10 Digit International Format
* Mobile Numnber: +(CC)-10 Digit Internation Format
* Month: Full Names, 3 Letter, Month Number, Month Between Range
* Week: Full Name of Days, 3 Letter, Week Number, Week Between Range
* Calendar Year: Full Year, Last 2 Digits, Year Between Range 
* Currency: ISO Currency, Full Name, Country Specific Currency
* Amount: Minor Unit, Major Unit, Amount with Decimal Precision, Amount with Before/After Decimal Precision
* Username: Length Based, Name Based, Quirky (AI featured*)
* Password: Length Based, Password, Passphrase
* Email: Real Domain, Fake Domain, Quirky (AI featured*)
* Domain Name: COM/ORG/IO, etc.
* File Name: Fixed Extension, Random Extension, Length Based
* File Path: Windows Style, Linux Style

### Synthetic Data Generator

### Libraries

### Design

#### High-level Design

#### Low-level Design

## Disclaimer
I am aware that there are advanced tools and services available online, along with well-established techniques that they may use. However, my primary goal with this implementation is to rely on my own understanding and learning to build a solution from scratch.  This approach allows me to thoroughly grasp the underlying concepts and work through the complexities of systems that handle large-scale, diverse datasets.

While I aim to improve this implementation over time by learning from other sources and solutions, I believe in first applying my own knowledge to fully internalize the challenges and principles. If you have suggestions or insights, I would greatly appreciate your feedback. Please feel free to connect with me via email.
