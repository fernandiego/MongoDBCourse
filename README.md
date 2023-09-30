# MongoDB Udemy course
- Excel in NoSQL & Pass Certification

## ROADMAP so far:
- Installing mongoDB using docker image [Tutorial how to](https://www.mongodb.com/docs/manual/tutorial/install-mongodb-community-with-docker/#std-label-docker-mongodb-community-install)
- local database created, with no auth, some issues here
- Lesson number 8, MongoDB origins and benefits
- Lesson number 9, the differences of MongoDB and SQL databases

### MongoDB terminologies
- It's like JSON structure
<details close>
<summary>click to see JSON</summary>
<img src="img/JsonSample.png" alt="Json sample">
</details>
<details close>
<summary>click to see MongoDB</summary>
<img src="img/MongoDBSample.png" alt="MongoDB sample">
</details>

### MongoDB benefits
 <details close>
   <summary>click to see</summary>
MongoDB offers several benefits that make it a popular choice for many applications:

1. **Flexible Schema:** MongoDB is a NoSQL database that uses a flexible document-based data model (BSON). It allows you to store data in a format similar to JSON, and each document in a collection can have a different structure. This flexibility is particularly useful for applications with evolving or dynamic data requirements.

2. **Scalability:** MongoDB is designed to scale horizontally, making it suitable for handling large volumes of data and high traffic loads. It supports sharding, which allows you to distribute data across multiple servers or clusters to ensure high availability and performance.

3. **High Performance:** MongoDB is known for its high read and write performance. It employs various optimization techniques like indexing, query optimization, and memory mapping to provide fast data access.

4. **Rich Query Language:** MongoDB provides a powerful query language that supports a wide range of query operations, including complex aggregations and geospatial queries. It also supports full-text search.

5. **Geospatial Data:** MongoDB has built-in support for geospatial data and queries, making it an excellent choice for location-based applications.

6. **Automatic Failover:** MongoDB supports automatic failover using replica sets. In the event of a primary node failure, one of the secondary nodes is automatically elected as the new primary, ensuring high availability.

7. **Document Indexing:** MongoDB allows you to create various types of indexes, including compound indexes and geospatial indexes, to improve query performance.

8. **Community and Ecosystem:** MongoDB has a large and active community of users and contributors. It also offers official drivers and client libraries for various programming languages, making it easy to integrate with your application.

9. **Aggregation Framework:** MongoDB provides a robust aggregation framework for performing complex data transformations and computations, allowing you to process and analyze data within the database.

10. **Schema Evolution:** MongoDB's flexible schema and versioning support make it easy to evolve your data model over time without requiring extensive migrations.

11. **Security Features:** MongoDB offers various security features, including authentication, role-based access control, encryption at rest and in transit, and auditing, to protect your data.

12. **Cloud Integration:** MongoDB Atlas, the official cloud-hosted MongoDB service, simplifies database management, scaling, and monitoring in a cloud environment. It integrates seamlessly with popular cloud providers.

While MongoDB has many advantages, it's essential to evaluate your specific use case and requirements to determine whether it's the right choice for your application.  

</details>

### MongoDB differences to SQL
<details close>
<summary>click to see</summary>
MongoDB and traditional SQL databases differ in several key ways:

1. **Data Model:**
   - **MongoDB:** MongoDB is a NoSQL database that uses a flexible, document-based data model. Data is stored in BSON (binary JSON) documents, and each document in a collection can have a different structure.
   - **SQL:** SQL databases use a structured, table-based data model. Data is organized into tables with predefined schemas consisting of rows and columns.

2. **Schema:**
   - **MongoDB:** MongoDB has a dynamic schema, which means you can change the structure of documents without affecting other documents in the same collection. This flexibility is useful for applications with evolving data requirements.
   - **SQL:** SQL databases have a rigid schema where the structure of tables and relationships between them are defined upfront. Changing the schema often requires complex migrations.

3. **Query Language:**
   - **MongoDB:** MongoDB uses a rich query language that includes support for querying nested documents, geospatial queries, and text search. Queries are expressed in a JSON-like format.
   - **SQL:** SQL databases use SQL (Structured Query Language) for querying data, which is a standardized language for relational databases. SQL offers powerful querying capabilities for structured data.

4. **Scaling:**
   - **MongoDB:** MongoDB is designed for horizontal scalability. It supports sharding, which allows data to be distributed across multiple servers or clusters to handle large data volumes and high traffic loads.
   - **SQL:** SQL databases typically scale vertically by adding more resources (CPU, RAM) to a single server. Scaling out can be challenging and may involve complex clustering solutions.

5. **ACID vs. BASE:**
   - **MongoDB:** MongoDB is often associated with the BASE (Basically Available, Soft state, Eventually consistent) model. It prioritizes high availability and partition tolerance over strong consistency, making it suitable for certain use cases like content management systems and real-time analytics.
   - **SQL:** SQL databases adhere to the ACID (Atomicity, Consistency, Isolation, Durability) properties, which guarantee strong consistency and transactional integrity. ACID is crucial for applications where data consistency is paramount, such as financial systems.

6. **Join Operations:**
   - **MongoDB:** MongoDB does not support traditional SQL-style joins between collections. Instead, it encourages denormalization and embedding related data within documents.
   - **SQL:** SQL databases excel at performing complex join operations between tables, allowing you to model and query normalized data efficiently.

7. **Complex Transactions:**
   - **MongoDB:** MongoDB supports multi-document transactions, but they are not as mature as SQL database transactions. Transactions are generally used for scenarios where data consistency is critical.
   - **SQL:** SQL databases offer robust support for complex transactions with features like rollback, commit, and savepoints.

8. **Schema Evolution:**
   - **MongoDB:** MongoDB's flexible schema makes it easier to evolve data models over time without significant schema migrations.
   - **SQL:** SQL databases require careful schema design and management, and schema changes can be complex and time-consuming.

The choice between MongoDB and SQL databases depends on your specific project requirements, data model, and use cases. Each has its strengths and weaknesses, and the decision should align with your application's needs.
</details>

