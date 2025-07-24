# DBMS Architecture Explained (LEC-2)

This document provides a detailed overview of Database Management System (DBMS) architecture, focusing on the Three-Schema Architecture, data models, languages, access methods, roles, and application architectures.

## 1. View of Data (Three-Schema Architecture)

The primary goal of a DBMS is to offer users an abstract view of data, hiding the complexities of how data is stored and maintained. This abstraction is achieved through several levels, enabling multiple users to access the same data with personalized views while storing the underlying data only once.

### a. Physical Level / Internal Level
* **Lowest level of abstraction.**
* Describes **how** the data is stored physically.
* Focuses on **low-level data structures**.
* Associated with the **Physical Schema**, which details the physical storage structure of the database.
* **Key aspects:** Storage allocation (e.g., N-ary trees), data compression, encryption.
* **Goal:** Define efficient algorithms for data access.

### b. Logical Level / Conceptual Level
* The **Conceptual Schema** describes the database's design at a conceptual level.
* Details **what data is stored** in the DB and the **relationships** among that data.
* Users at this level are **unaware of physical-level structures**.
* Primarily used by the **Database Administrator (DBA)** to decide what information to maintain in the DB.
* **Goal:** Ease of use for database design and management.

### c. View Level / External Level
* **Highest level of abstraction.**
* Aims to **simplify user interaction** by providing different views to different end-users.
* Each **View Schema (or Subschema)** describes the portion of the database relevant to a particular user group, hiding the rest.
* Acts as a **security mechanism** to restrict user access to specific parts of the DB.

## 2. Instances and Schemas

* **Instance:** The collection of information stored in the DB at a particular moment in time. This changes frequently.
* **Schema:** The overall design or structural description of the database. Schemas generally do not change frequently.
* DB schema corresponds to variable declarations (along with their types) in a programming language.
* **Types of Schemas:** Physical, Logical, and several View Schemas (subschemas).
* The **Logical Schema** is the most crucial for application programs, as programmers build applications using this level of abstraction.
* **Physical Data Independence:** A key goal is that changes to the physical schema should not necessitate changes to the logical schema or application programs.

## 3. Data Models

* Provide a way to describe the database's design at the logical level.
* A collection of conceptual tools for describing data, data relationships, data semantics, and consistency constraints.
* **Examples:**
    * Entity-Relationship (ER) Model
    * Relational Model
    * Object-Oriented Model
    * Object-Relational Data Model

## 4. Database Languages

DBMS systems typically include specialized languages for defining and manipulating data.

### a. Data Definition Language (DDL)
* Used to **specify the database schema**.
* Allows defining consistency constraints that must be enforced during DB updates.

### b. Data Manipulation Language (DML)
* Used to **express database queries and updates**.
* **Data manipulation involves:**
    * Retrieval of information.
    * Insertion of new information.
    * Deletion of existing information.
    * Updating existing information.
* A **Query Language** is a part of DML used specifically for retrieving information.

### c. Practical Implementation
* In practice, both DDL and DML features are often integrated into a single database language, such as **SQL (Structured Query Language)**.

## 5. How is a Database Accessed from Application Programs?

Application programs, typically written in host languages like C/C++ or Java, interact with the database.

* Applications execute DML statements from the host language to access the DB (e.g., a banking system's payroll module).
* **APIs (Application Programming Interfaces)** are provided to send DML/DDL statements to the DB and retrieve results.
    * **ODBC (Open Database Connectivity):** A standard API for accessing database management systems. Commonly used with C/C++.
    * **JDBC (Java Database Connectivity):** A Java API for connecting to and interacting with databases.

## 6. Database Administrator (DBA)

The DBA is a crucial role responsible for the central control of both the data and the programs that access it.

### Functions of a DBA:
* **Schema Definition:** Defining and maintaining the database schema.
* **Storage Structure and Access Methods:** Deciding on efficient storage structures and access paths.
* **Schema and Physical Organization Modifications:** Managing changes to the database schema and physical layout.
* **Authorization Control:** Granting and revoking access permissions to users.
* **Routine Maintenance:**
    * Performing periodic backups.
    * Applying security patches and updates.
    * Managing any database upgrades.

## 7. DBMS Application Architectures

These architectures describe how client machines (where remote users work) interact with server machines (where the DB system runs).

### a. Tier-1 Architecture (Single-Tier)
* The client, server, and database all reside on the **same machine**.
* Typically used for personal databases or very simple applications.

### b. Tier-2 Architecture (Two-Tier)
* The application is partitioned into **two main components**:
    1.  **Client Machine:** Hosts the user interface and the application logic that directly invokes database system functionality.
    2.  **Server Machine:** Runs the Database Management System (DBMS).
* The client machine communicates with the server machine by sending **query language statements (e.g., SQL)**.
* **API standards** like **ODBC (Open Database Connectivity)** and **JDBC (Java Database Connectivity)** are used to facilitate communication between the client and the database server.

### c. Tier-3 Architecture (Three-Tier)
* The application is partitioned into **three logical components**:
    1.  **Client Machine (Presentation Tier):** This is typically a thin client (e.g., a web browser) that serves as the frontend. It **does not contain any direct database calls**.
    2.  **Application Server (Logic/Middle Tier):** This layer contains the **business logic** (what actions to take under specific conditions). The client machine communicates with this application server.
    3.  **Database System (Data Tier):** The application server communicates with the database system to access data.
* **Best suited for WWW (World Wide Web) Applications** due to its scalability and security benefits.

#### Advantages of Three-Tier Architecture:
* **Scalability:** Due to the distribution of application servers, the system can scale horizontally by adding more application server instances to handle increased load.
* **Data Integrity:** The application server acts as a middle layer between the client and the database, which centralizes business logic and minimizes the chances of data corruption by enforcing rules before data reaches the DB.
* **Security:** Clients cannot directly access the database, as all requests must pass through the application server. This adds a crucial layer of security, protecting the database from direct exposure to the client.
