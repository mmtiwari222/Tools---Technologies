# LEC-1: Introduction to DBMS

## 1. What is Data?
- Data is a collection of raw, unorganized facts and details like text, observations, figures, symbols, and descriptions of things etc.  
  - In other words, **data does not carry any specific purpose and has no significance by itself**.  
  - Data is measured in terms of bits and bytes – which are basic units of information in the context of computer storage and processing.
- Data can be recorded and doesn't have any meaning unless processed.

## 2. Types of Data
### a. Quantitative
- Numerical form  
- Weight, volume, cost of an item.

### b. Qualitative
- Descriptive, but not numerical.  
- Name, gender, hair color of a person.

## 3. What is Information?
- Info. is **processed, organized, and structured data**.
- It provides **context of the data** and enables **decision making**.
- Processed data that **makes sense** to us.
- Information is extracted from the data, by **analyzing and interpreting** pieces of data.
- Example:
  - You have data of all the people living in your locality (data). When you analyze and interpret the data and come to some conclusion that:
    1. There are 100 senior citizens.
    2. The sex ratio is 1:1.
    3. Newborn babies are 100.
  - These are **information**.

## 4. Data vs Information
- Data is a collection of facts, while information puts those facts into context.
- While data is raw and unorganized, information is organized.
- Data points are individual and sometimes unrelated. Information maps out that data to provide a big-picture view of how it all fits together.
- Data, on its own, is meaningless. When it’s analyzed and interpreted, it becomes meaningful information.
- Data does not depend on information; however, information depends on data.
- Data typically comes in the form of graphs, numbers, figures, or statistics. Information is typically presented through words, language, thoughts, and ideas.
- Data isn’t sufficient for **decision-making**, but you can make decisions based on information.

## 5. What is a Database?
- A database is an electronic place/system where data is stored in a way that it can be easily **accessed, managed, and updated**.
- To make real use of data, we need **Database Management Systems (DBMS)**.

## 6. What is DBMS?
- A **Database Management System (DBMS)** is a collection of **interrelated data** and a **set of programs** to access those data.  
- The collection of data, usually referred to as the **database**, contains information relevant to an enterprise.
- The primary goal of a DBMS is to provide a way to store and **retrieve database information** that is both convenient and efficient.
- A DBMS is the database itself, along with all the software and functionality. It is used to perform different operations, like **accessing**, **updating**, and **deletion** of the data.

## 7. DBMS vs File Systems

### a. File-processing systems have major disadvantages:

1. **Data Redundancy and Inconsistency**  
   - Redundancy refers to storing the same data in multiple files.  
   - Inconsistency arises when these copies are not updated simultaneously, leading to conflicting data.

2. **Difficulty in Accessing Data**  
   - Data retrieval requires complex, manual programming.  
   - There’s no unified query system, making access inefficient and time-consuming.

3. **Data Isolation**  
   - Data is scattered across different files and formats.  
   - Combining data from multiple files becomes difficult due to lack of linkage.

4. **Integrity Problems**  
   - Enforcing rules like unique IDs or valid ranges is challenging.  
   - It must be handled manually, which increases the chance of errors.

5. **Atomicity Problems**  
   - Transactions may fail midway, leaving data in an inconsistent state.  
   - There's no guarantee that operations will be fully completed or rolled back.

6. **Concurrent-Access Anomalies**  
   - Multiple users accessing files simultaneously may cause conflicts.  
   - Changes made by one user can be overwritten by another without notice.

7. **Security Problems**  
   - Limited access controls in file systems.  
   - Hard to enforce different levels of access (read, write, delete) for different users.

### b. These 7 disadvantages are also the **Advantages of DBMS**