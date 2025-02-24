
# **Database Concepts: Complete Notes**

This repository contains detailed notes on essential database concepts, covering topics such as normalization, attributes, keys, cardinalities, and more. These concepts are critical for database design and management, making them an invaluable resource for your studies or exam preparation.

## **Table of Contents**

1. [Normalization Types](#1-normalization-types)
2. [Attribute Types](#2-attribute-types)
3. [Key Types](#3-key-types)
4. [Mapping Cardinalities](#4-mapping-cardinalities)
5. [Entity Sets](#5-entity-sets)
6. [Relationship Sets](#6-relationship-sets)
7. [E-R Diagram (Entity-Relationship Diagram)](#7-e-r-diagram-entity-relationship-diagram)
8. [Weak Entity Sets](#8-weak-entity-sets)
9. [Strong Entity Sets](#9-strong-entity-sets)

---

## **1. Normalization Types**

Normalization is a method to organize data in a database to minimize redundancy and ensure data integrity. Here are the different normal forms explained:

- **1NF (First Normal Form):**  
  The table is in 1NF if it contains only atomic (indivisible) values, meaning each column holds a single value, not a list or set. There should be no repeating groups in the rows.

- **2NF (Second Normal Form):**  
  The table is in 2NF if it is in 1NF and all non-key attributes are fully dependent on the primary key. This removes partial dependencies, where a non-key attribute depends only on part of the primary key (in case of composite keys).

- **3NF (Third Normal Form):**  
  The table is in 3NF if it is in 2NF and has no transitive dependencies. Transitive dependency happens when one non-key attribute depends on another non-key attribute.

- **BCNF (Boyce-Codd Normal Form):**  
  BCNF is a stricter version of 3NF. It ensures that every determinant is a candidate key. A determinant is any attribute (or set of attributes) that determines another attribute.

- **4NF (Fourth Normal Form):**  
  The table is in 4NF if it is in BCNF and does not contain multi-valued dependencies. A multi-valued dependency occurs when one attribute uniquely determines a set of values for another attribute.

- **5NF (Fifth Normal Form):**  
  The table is in 5NF if it is in 4NF and there is no join dependency. Join dependency occurs when a table can be decomposed into smaller tables without losing information.

- **6NF (Sixth Normal Form):**  
  6NF is used for temporal databases (databases that track time). It further reduces redundancy and focuses on dividing a table into smaller tables to store data over time.

---

## **2. Attribute Types**

Attributes are characteristics or properties of an entity. Let's explore the types of attributes:

- **Simple (Atomic) Attribute:**  
  This is a basic attribute that cannot be divided further. For example, "Age" is a simple attribute because it is a single value.

- **Composite Attribute:**  
  A composite attribute can be divided into smaller sub-parts. For example, "Full Name" can be divided into "First Name" and "Last Name".

- **Derived Attribute:**  
  This is an attribute that can be computed from other attributes. For example, "Age" can be derived from the "Date of Birth".

- **Multi-valued Attribute:**  
  This attribute can hold multiple values for a single entity. For example, "Phone Numbers" can be a multi-valued attribute for a person.

- **Key Attribute:**  
  This is an attribute that uniquely identifies an entity. For example, "Student ID" is a key attribute for the Student entity.

- **Stored Attribute:**  
  These attributes are stored directly in the database. For example, "Date of Birth" is stored as a raw value, whereas "Age" is derived from it.

---

## **3. Key Types**

Keys are used to uniquely identify records in a table. Here's a breakdown of key types:

- **Primary Key:**  
  A primary key uniquely identifies each record in a table. It cannot contain NULL values. For example, "Student ID" serves as the primary key in a student table.

- **Candidate Key:**  
  Candidate keys are attributes or sets of attributes that could serve as a primary key. There can be multiple candidate keys, but only one is chosen as the primary key.

- **Super Key:**  
  A superkey is any set of attributes that can uniquely identify a record. A superkey can have extra attributes that are unnecessary for uniqueness.

- **Foreign Key:**  
  A foreign key is an attribute that creates a link between two tables by referencing the primary key of another table. It helps maintain relationships between tables.

- **Composite Key:**  
  A composite key is a primary key that consists of more than one attribute. It is used when a single attribute is not enough to uniquely identify a record.

- **Alternate Key:**  
  These are candidate keys that were not chosen as the primary key. They can still uniquely identify records.

- **Surrogate Key:**  
  A surrogate key is a system-generated key that uniquely identifies records. It is often an auto-incremented number that has no real-world meaning.

---

## **4. Mapping Cardinalities**

Cardinality refers to the number of instances of one entity that can be or must be associated with each instance of another entity. The types include:

- **One-to-One (1:1):**  
  One entity is related to exactly one other entity. For example, a "Person" might have one "Passport".

- **One-to-Many (1:M):**  
  One entity is related to many other entities. For example, one "Department" has many "Employees".

- **Many-to-One (M:1):**  
  Many entities are related to one entity. For example, many "Employees" belong to one "Department".

- **Many-to-Many (M:N):**  
  Many entities are related to many other entities. For example, many "Students" take many "Courses".

---

## **5. Entity Sets**

An entity set is a collection of similar entities. The different types are:

- **Strong Entity Set:**  
  A strong entity set can exist independently and has a primary key. For example, "Employee" can exist without needing another entity.

- **Weak Entity Set:**  
  A weak entity set depends on a strong entity set for its identification and lacks a primary key. For example, a "Dependent" entity relies on an "Employee" entity for identification.

- **Entity Instance:**  
  An entity instance is a specific occurrence of an entity. For example, "John Doe" is an entity instance of the "Employee" entity.

---

## **6. Relationship Sets**

Relationship sets define how entities are related. The types are:

- **Unary Relationship:**  
  A relationship between instances of the same entity set. For example, an "Employee" manages other "Employees" in a unary relationship.

- **Binary Relationship:**  
  A relationship between two entity sets. For example, a "Student" enrolls in a "Course".

- **Ternary Relationship:**  
  A relationship involving three entity sets. For example, a "Project" involves an "Employee" and a "Department".

- **N-ary Relationship:**  
  A relationship involving more than three entity sets.

---

## **7. E-R Diagram (Entity-Relationship Diagram)**

An ER diagram visually represents entities and their relationships. Here's how the components are represented:

- **Rectangles:** Represent entity sets.
- **Ellipses:** Represent attributes of entities.
- **Diamonds:** Represent relationships.
- **Lines:** Connect entities to attributes and relationships.
- **Double Rectangles:** Represent weak entity sets.

---

## **8. Weak Entity Sets**

A weak entity set does not have a primary key and depends on a strong entity set for its identification. It uses a partial key to identify records. For example, an "Order Item" depends on an "Order" entity.

---

## **9. Strong Entity Sets**

A strong entity set has a primary key and can exist independently. It does not depend on any other entity for identification. For example, an "Employee" entity exists independently with a unique "Employee ID".

---

These detailed notes should provide you with a clear understanding of key database concepts, from normalization and attributes to keys and relationships. If you have any questions or need further clarification, feel free to reach out!

---

