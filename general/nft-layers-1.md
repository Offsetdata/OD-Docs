# Data Security

## Introduction:

Offsetdata takes data security seriously and implements industry best practices to protect user data. We believe in being transparent about our data handling procedures. This document outlines how we store and secure data to maintain user privacy and exceed industry standards.

Here are some of the key measures we take to keep data safe:

### Authentication on Offsetdata

Offsetdata user authentication and access control provider Auth0. Auth0 is an industry-leading identity platform with top-grade security to prevent breaches and attacks. Auth0 maintains high-security certifications like ISO 27001, SOC 2, and FedRAMP.

* High availability with 99.99% uptime SLA to prevent downtime.

By leveraging Auth0, we ensure secure and reliable authentication and authorization for our application and users. Auth0 gives us an enterprise-grade identity platform without the high costs of developing and maintaining it ourselves.

### Data Processing

Offsetdata leverages GraphQL for efficient and secure data querying and manipulation. GraphQL provides several advantages for data security:

* **Granular access control** - GraphQL allows defining precise permissions at the field level to restrict data access. Only specific data is exposed to clients based on their access requirements.
* **Filtering and pagination** - GraphQL queries can filter and paginate response data. This prevents overfetching and minimizing data exposure.
* **Validation** - Strong input validation prevents malformed queries that could expose unintended data.
* **Authentication** - Queries can be securely authenticated to verify the requester's identity.
* **Server-side processing** - GraphQL queries are executed on the server. This provides better protection compared to direct database access via clients.

By using GraphQL, Offsetdata limits data exposure to only what is explicitly requested per user. The granular control, filtering, and validation ensure unauthorized parties cannot access sensitive data or overload our servers with expensive queries.

GraphQL gives Offsetdata a robust and secure method for handling data requests and mutations from client apps. All data processing adheres to the principle of least privilege for end users and systems.

### API Authentication

For added security, Offsetdata requires authentication for all API requests. API consumers must first register and obtain an API key to make authorized requests.

API keys provide the following benefits:

* All API requests can be traced back to a specific key owner for auditing and access control.
* API keys can be rotated or revoked at any time to block bad actors.
* Rate limiting and quotas can be applied per API key to prevent abuse.
* Keys can be restricted to specific IP addresses, referer URLs, or endpoints.

By requiring API authentication via keys, Offsetdata ensures all API access is accountable and manageable. The keys prevent anonymous abuse of our interfaces while allowing trusted partners to integrate with our systems.

### Data Hosting

Offsetdata uses the MongoDB Atlas database hosted on Microsoft Azure for faster data processing. Both MongoDB Atlas and Azure have achieved ISO/IEC 27001:2013 certification for information security management.

### Data Hashing

All data queries for storage submitted via Offsetdata are hashed using SHA-256 and salted before being stored on the blockchain. This ensures unauthorized parties cannot read the data. The salting is done by generating a unique salt for each data record on the Offsetdata side.

### Blockchain Storage

The hashed and salted data is stored on the blockchain, making it immutable and transparent. Access to the data is strictly controlled through permissions granting, ensuring GDPR compliance. Only parties with explicit access can view the data.

By using best-in-class providers, encryption, salting, and blockchain technology, Offsetdata keeps user data safe and secure. Our processes are designed to exceed industry standards for data protection.

### Hosting Infrastructure

Offsetdata leverages Google Cloud Platform (GCP) to host our application servers and external APIs.&#x20;

Our specific hosting setup includes:

* World-class data centers with high physical security measures.
* DDoS protection and mitigation against attacks.
* Network security features like private VPC, firewalls, SSL encryption.
* Identity and access management to control internal access.
* Geographic redundancy across regions and zones.
* Built-in DDoS, SQL injection, and XSS protections.
* APIs hosted on GCP App Engine for auto-scaling.
* Web application hosted on GCP Compute Engine VMs.
* Data is stored in Cloud Storage buckets with versioning enabled.
* Databases running on managed Cloud SQL service.
* Distributed caching is provided by Memorystore.
* All internal traffic is encrypted under HTTPS.

By leveraging GCP's security-focused infrastructure, Offsetdata secures the application, APIs, and data from external threats while maintaining high availability. Our defence-in-depth strategy across network, platform, and application layers ensures a secure and robust hosting environment.
