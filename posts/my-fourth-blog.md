---
title: From Wireframe to Database
date: 2026-05-01
author: Qiuyue Xu
summary: Translating interface design into a structured and functional data model
tags:
  - Data Definition Document
  - Entity Relationship Diagram
---
Building on the wireframe developed in the previous stage, I began translating interface elements into structured data. To do this, I printed the wireframe and systematically identified each data element, including item names, prices, descriptions, images, tags, and transaction types. Each element was tagged based on its role (displayed, input, or generated). This step helped shift my perspective from interface components to underlying data attributes, enabling a clearer understanding of what the system must store and manage.

The Data Definition Document (DDD) was then constructed to set up such attributes into formal structures. During this process, an important issue emerged regarding how to represent tags. Initially, I considered storing tags as a list within each item. However, this approach quickly felt problematic, as it required placing multiple values within a single attribute. This “discomfort” indicated a violation of basic data structuring principles and revealed the presence of a hidden entity. As a result, tags were separated into their own table, transforming them from a property into an independent entity.

![Data Definition Document](../dist/assets/images/DDD.png)

The ERD was developed to represent relationships between entities. A key design decision was modelling the relationship between items and tags as many-to-many. Since an item can have multiple tags and each tag can be applied to multiple items, a junction table (item_tags) was introduced. This ensures flexibility and enables efficient querying using JOIN operations.

![Entity Relationship Diagram](../dist/assets/images/ERD.png)

Following this, an Entity Relationship Diagram (ERD) was created to define how entities interact. A key design decision was modelling the relationship between items and tags as many-to-many. An item can have multiple tags, and each tag can apply to multiple items. To resolve this, a junction table (item_tags) was introduced. This design ensures flexibility, avoids data duplication, and supports efficient querying using JOIN operations. It also demonstrates an understanding of relational structure beyond simply listing attributes.

The ERD was then implemented as a working database using SQLite. Tables were created with CREATE TABLE statements, and sample data was inserted to test functionality. This step was essential in validating that the conceptual model could operate within a real system. By executing SQL queries and JOIN operations, I confirmed that relationships between items and tags behaved as expected, demonstrating alignment between design decisions and technical implementation.

This process highlights the distinction between interface design and data modelling. While the wireframe focuses on user experience and visual structure, the DDD and ERD address how information is organised, stored, and retrieved. Identifying hidden entities and resolving many-to-many relationships not only improved the logical consistency of the system but also enhanced its scalability for future development.

Overall, this stage reflects a transition from conceptual design to technical realisation, where design decisions are informed by both user needs and system constraints. This alignment between functional requirements and data structure is critical in developing robust and maintainable web applications.