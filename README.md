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

* Design Patterns,SOLID Principles, Polymorphism
* Memory Management, Caching, Object Handling
* Multithreading, Synchronization
* Data Manipulation, String Handling
* Scaling, Traffic Handling
* Resource Utilization & Optimization
* Validations, Exception Handling
* Authentication, Security, Monitoring
* Data-store management, Decentralized Truth Store

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

There are better tools & services available online and I am aware of certain techniques what they might be using.  
This is, however, in its simplest form, my way of implementing this requirement. I am building this to learn concepts  
and go through the complexities of similar systems that deal with huge amount of data of different varieties. I am  
definitely aiming to read more about the topic, learn other ways to do the same thing and hence keep enhancing the  
implementation. If you're reading this, and have suggestions for me, feel free to connect on my email `hpx.io@keemail.me`.
