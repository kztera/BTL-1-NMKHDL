<h1>Chapter 6: Join the NoSQL movement</h1>

<h2>Table of Content</h2>

- [Part 1: NoSQL databases](#part-1-nosql-databases)
  - [What is NoSQL? (Not Only Structured Query Language)](#what-is-nosql-not-only-structured-query-language)
  - [Why do they exist?](#why-do-they-exist)
  - [Why not until recently?](#why-not-until-recently)
  - [What are the main differences between NoSQL and relational databases?](#what-are-the-main-differences-between-nosql-and-relational-databases)
  - [How NoSQL databases rewrite ACID into BASE principles](#how-nosql-databases-rewrite-acid-into-base-principles)
  - [Why the CAP theorem is important for multi-node database setup](#why-the-cap-theorem-is-important-for-multi-node-database-setup)
  - [What types are there and why should you care?](#what-types-are-there-and-why-should-you-care)
- [Part 2: NoSQL databases in practice: What disease is that?](#part-2-nosql-databases-in-practice-what-disease-is-that)
  - [What is the problem we are trying to solve?](#what-is-the-problem-we-are-trying-to-solve)
  - [What is the process we are going to follow?](#what-is-the-process-we-are-going-to-follow)
  - [Requirements for the project](#requirements-for-the-project)
  - [Setting up Elasticsearch locally](#setting-up-elasticsearch-locally)



<h2>This chapter covers</h2>

- Understanding NoSQL databases and why they're used today
- Identifying the different NoSQL and relational databases
- Defining the ACID principle and how it relates to the NoSQL BASE principle
- Learning why the CAP theorem is important for multi-node database setup
- Applying the data science process to a project with the NoSQL database Elasticsearch

## Part 1: NoSQL databases

> We’ll look into NoSQL databases in general and answer these questions: Why do they exist? Why not until recently? What types are there and why should you care?

### What is NoSQL? (Not Only Structured Query Language)

NoSQL is a type of database management system that is designed to handle large volumes of unstructured or semi-structured data. Unlike traditional relational databases, NoSQL databases do not rely on a fixed schema and are highly scalable and flexible. They are often used in big data applications, web applications, and other scenarios where data needs to be processed quickly and efficiently.

### Why do they exist? 

NoSQL databases are designed to address the limitations of traditional relational databases, which were designed to handle structured data and run on a single server. As data volumes grew and more complex data structures emerged, it became clear that a new type of database was needed that could handle unstructured or semi-structured data, scale horizontally across multiple servers, and provide high availability and fault tolerance. NoSQL databases were developed to meet these needs and have become increasingly popular in recent years due to their flexibility, scalability, and performance advantages over traditional relational databases.

### Why not until recently?

NoSQL databases have been around for several decades, but they were not widely adopted until recently due to several factors. They were originally designed to handle large volumes of unstructured data, which was not a common problem in the past. However, with the rise of big data and the Internet of Things (IoT), more and more companies are generating massive amounts of unstructured data that needs to be processed quickly and efficiently. Traditional relational databases were the dominant technology for many years and well-established in the industry, contributing to the slower adoption of NoSQL databases.

Early NoSQL databases lacked some of the features and functionality of relational databases, such as support for transactions and complex queries. However, as data volumes grew and new use cases emerged, NoSQL databases evolved to become more robust and feature-rich. Advancements in cloud computing and distributed systems also played a significant role in the increased adoption of NoSQL databases. These advancements made it easier to deploy and manage NoSQL databases at scale, further fueling their popularity.

### What are the main differences between NoSQL and relational databases?

The main differences between NoSQL and relational databases are:

1. Data model: Relational databases use a tabular data model with fixed schemas, while NoSQL databases use flexible data models that can handle unstructured or semi-structured data.

2. Scalability: Relational databases are typically designed to run on a single server and scale vertically, while NoSQL databases are designed to scale horizontally across multiple servers.

3. Querying: Relational databases use SQL (Structured Query Language) for querying data, while NoSQL databases use various query languages or APIs depending on the type of database.

4. ACID compliance: Relational databases are typically ACID-compliant, meaning they guarantee consistency, isolation, durability, and atomicity of transactions. NoSQL databases may sacrifice some of these guarantees in favor of scalability and performance.

5. Cost: Relational databases can be expensive to license and maintain, especially for large-scale deployments. NoSQL databases are often open source or have lower licensing costs, making them more cost-effective for certain use cases.

Overall, the choice between a relational database and a NoSQL database depends on the specific needs of your application. If you have structured data that requires complex querying and transactional consistency, a relational database may be the best choice. If you have unstructured or semi-structured data that requires high scalability and performance at scale, a NoSQL database may be a better fit.

### How NoSQL databases rewrite ACID into BASE principles

NoSQL databases rewrite ACID (Atomicity, Consistency, Isolation, Durability) into BASE (Basically Available, Soft state, Eventually consistent) principles to work better in a distributed fashion. 

ACID is a set of properties that guarantee the reliability and consistency of transactions in a relational database. However, these properties can be difficult to maintain in a distributed environment where data is spread across multiple nodes. 

BASE principles provide an alternative approach that prioritizes availability and partition tolerance over strict consistency. Basically Available means that the system should always be available for read and write operations even if some nodes fail. Soft state means that the system can tolerate temporary inconsistencies or conflicts between nodes. Eventually consistent means that the system will eventually converge to a consistent state over time.

By adopting BASE principles, NoSQL databases can achieve high scalability and fault tolerance while still providing acceptable levels of consistency for many use cases. However, it's important to note that not all NoSQL databases follow BASE principles - some may still prioritize strict consistency over availability or partition tolerance depending on their specific use case.

### Why the CAP theorem is important for multi-node database setup

The CAP theorem is important for multi-node database setups because it highlights the trade-offs that must be made when designing a distributed system. The CAP theorem states that in a distributed system, it is impossible to simultaneously achieve all three of the following guarantees:

1. Consistency: Every read operation receives the most recent write or an error.

2. Availability: Every non-failing node returns a response for all read and write requests in a reasonable amount of time.

3. Partition tolerance: The system continues to function even when network partitions occur, meaning that nodes are unable to communicate with each other.

In other words, when designing a distributed database system, you can only choose two out of three guarantees - consistency, availability, and partition tolerance. This means that you must make trade-offs between these guarantees based on your specific use case and requirements.

For example, if you prioritize consistency and partition tolerance, you may sacrifice availability during network partitions. If you prioritize availability and partition tolerance, you may sacrifice consistency by allowing temporary inconsistencies between nodes.

Understanding the CAP theorem is important for designing and operating multi-node database systems because it helps developers make informed decisions about how to balance these trade-offs based on their specific needs and constraints.


### What types are there and why should you care?

There are several types of NoSQL databases, including document stores, key-value stores, column-family stores, and graph databases. Each type is designed to handle different types of data and use cases. 

Document stores are ideal for storing and querying semi-structured data such as JSON or XML documents. Key-value stores are optimized for high-speed read and write operations on simple data structures such as strings or integers. Column-family stores are designed to handle large volumes of structured data with high write throughput. Graph databases are used to store and query complex relationships between entities.

You should care about the different types of NoSQL databases because each type has its own strengths and weaknesses, and choosing the right type for your application can have a significant impact on performance, scalability, and cost. By understanding the different types of NoSQL databases and their use cases, you can make an informed decision about which one is best suited for your needs.

## Part 2: NoSQL databases in practice: What disease is that?

> We’ll tackle a real-life problem—disease diagnostics and profiling—using freely available data, Python, and a NoSQL database.


### What is the problem we are trying to solve?

The problem that we are trying to solve in the case study is to build a disease diagnostic system using data exploration techniques. The goal is to create a search engine that can help general practitioners diagnose diseases by inputting a set of symptoms. 

The case study focuses on exploring a dataset of disease symptoms and diagnoses using text search queries, and building a system that can predict the most likely diagnosis based on the input symptoms. The aim is to provide a practical example of how data exploration techniques can be used to solve real-world problems in healthcare and other domains.

The chapter provides step-by-step guidance on how to approach this problem, including how to preprocess the data, build an index for efficient searching, and evaluate the performance of our system. We will also explore different techniques for improving the accuracy of our predictions, such as using machine learning algorithms or incorporating additional data sources.

### What is the process we are going to follow?

The process can be broken down into several steps:

1. Setting the research goal: The first step is to define the research goal, which is to build a search engine that can help diagnose diseases based on input symptoms.

2. Data collection: The next step is to collect data from a source such as Wikipedia. In this case study, Wikipedia is used as a single source for demonstration purposes.

3. Data preparation: Once the data has been collected, it may need to be cleaned and preprocessed to ensure that it is in a suitable format for analysis.

4. Data exploration: This step involves using text search queries to explore the dataset of disease symptoms and diagnoses, and building an index for efficient searching.

5. Model building: No real data modeling is applied in this chapter. Documentterm matrices that are used for search are often the starting point for advanced topic modeling. We won’t go into that here.

6. Presenting results: The final step is to present the results of our analysis in a clear and concise manner, such as a report or presentation. In this chapter we won't go so far as to build an actual interface.

### Requirements for the project

- Python3 with the following packages: elasticsearch and wikipedia
- A locally set up Elasticsearch instance
- The IPython library for Jupyter notebooks

### Setting up Elasticsearch locally

- Download and install `elasticsearch` and `kibana` from https://www.elastic.co/downloads/elasticsearch and https://www.elastic.co/downloads/kibana 
- Then unzip the files and run the executables from bin folder
- Elasticsearch will run on port 9200 and Kibana on port 5601 

---

Read full in the Slide Summary [here](https://www.canva.com/design/DAFkflFgle8/YvoRZ58WOnUa02wlU9FqpA/edit?utm_content=DAFkflFgle8&utm_campaign=designshare&utm_medium=link2&utm_source=sharebutton) if for Canva Presentation version or PDF version [here](slide/Chapter_6_Summary.pdf)