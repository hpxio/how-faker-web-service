# Faker Web Service

> Hands-on-With Faker Web Service, which enables client to generate data of specific structure in bulk.

## Objective

Faker Web Service (a.k.a FakerWS in short) will allow users to generate structured data in bulk.  
The data is generated on the fly as per the specifications given by the user. All APIs are stateless  
by design. The main objective of this work is to learn system-design internals of a service which generates  
huge amount of data and sends over web.   

There are lot of learning scopes with this simple example like non-functional challenges like compute resources,  
memory management, validations, security, load-balancing and functional challenges like producing consistent results,  
handling request-response in right format, header management & manipulation, etc.

## Expectations
Expected to learn following key concepts

* Design Patterns,SOLID Principles, Polymophism
* Memory Management, Caching, Object Handling
* Multithreading, Synchronization
* Data Manipulation, String Handling
* Scaling, Traffic Handling
* Resource Utilization & Optimization
* Validations, Exception Handling
* Authentication, Security, Monitoring

## Scopes

The application is capable of generating following types of structured data:

* JSON Payload
* CSV Data
* SQL Statements

### Faker Data Types

* Date
* Time
* First Name
* Last Name
* Middle Name
* City
* State
* Country
* Address
* Pin Code
* Telephone Number
* Mobile Numnber
* UUID/GUID
* Month Names
* Week Days
* Calendar Year
* Season
* Number
* Decimal
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
* File Name
* File Path
* Custom Function

#### Multi-Format Support

* Date: ISO, DDMMYYY, etc.
* Time: Epoch, Nano, Milli, ISO, Timezone Based, HHMMSS, etc.
* Number: Short Number, Long Number,
* TBD

### Synthetic Data Generator

### Libraries

### Design

#### High-level Design

#### Low-level Design

## Disclaimer

There are better tools & services available online and I am aware of certain techniques what they might be using.  
This is, however, in its simplest form, my way of implementing this requirement. I am building this to learn concepts  
and go through the complexities of similar systems that deal with huge amount of data of different varieties. I am  
definitely aiming to read more about the topic, learn other ways to do the same thing and hence keep enhancing the  
implementation. If you're reading this, and have suggestions for me, feel free to connect on my email `hpx.io@keemail.me`.
