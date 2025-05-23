# **Database Concepts: Simple Notes**

This repo is all about explaining database concepts in the simplest way possible! Whether you're just getting started with databases or need a refresher, these notes should help. We’ll cover everything from normalization to entity sets and keys, all in a way that's easy to understand.

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

So, normalization is all about making your database neat and tidy, reducing unnecessary repetition and making sure things are in the right place. Here's what each normal form (NF) means:

- **1NF (First Normal Form):**  
  Think of this as just making sure each column has just one thing. Like, if you had a column for "Phone Numbers", you wouldn't put multiple numbers in the same cell—each one gets its own spot.

- **2NF (Second Normal Form):**  
  This is where we make sure that all the non-key stuff depends on the whole key, not just part of it. It means getting rid of weird cases where a piece of data only depends on part of the identifier (if it's a combo of things).

- **3NF (Third Normal Form):**  
  Now, we want to get rid of anything that depends on something that isn’t the main key. So if "Age" depends on "Birth Date", and "Birth Date" is just there to help identify the "Person", that's a problem. Everything should depend directly on the key.

- **BCNF (Boyce-Codd Normal Form):**  
  BCNF is stricter than 3NF. It’s making sure that anything that can determine something else (called a "determinant") is a key. If it’s not a key, it shouldn’t be able to define other stuff.

- **4NF (Fourth Normal Form):**  
  4NF takes care of situations where one thing is linked to multiple things at once. If one column determines a set of values in another column, we fix that here.

- **5NF (Fifth Normal Form):**  
  5NF makes sure that you can break your table down into smaller ones without losing any information. If a table can be split into pieces without any issue, it’s in 5NF.

- **6NF (Sixth Normal Form):**  
  6NF is a special case, usually for databases that track time. It makes your tables even more specific, dividing them further to avoid repetition over time.

---

## **2. Attribute Types**

Attributes are like the characteristics of the things you’re storing in your database. Here's the rundown of different attribute types:

- **Simple (Atomic) Attribute:**  
  These are basic things that can’t be broken down any further. For example, "Age" or "Phone Number" is just one thing.

- **Composite Attribute:**  
  This is like "Full Name", which you can break down into "First Name" and "Last Name".

- **Derived Attribute:**  
  Think of this as something that can be calculated from other stuff. For instance, "Age" can be figured out from "Date of Birth".

- **Multi-valued Attribute:**  
  Some things can have multiple values. For example, a person might have more than one phone number or email address.

- **Key Attribute:**  
  This is an attribute that’s used to uniquely identify an entity. For example, "Student ID" in a student table.

- **Stored Attribute:**  
  These are just regular attributes that are directly stored in the database. For example, "Date of Birth" is stored directly, while "Age" might be calculated from it.

---

## **3. Key Types**

Keys are used to find data easily and make sure everything is unique. Here’s a breakdown of the different key types:

- **Primary Key:**  
  The main key that uniquely identifies a record. It can’t be empty (NULL). For example, "Student ID" is the primary key for the student table.

- **Candidate Key:**  
  These are like alternate options for a primary key. There might be several ways to uniquely identify something, but only one gets picked.

- **Super Key:**  
  A superkey is just any set of columns that can uniquely identify a record. It might have extra columns that aren’t really necessary for uniqueness.

- **Foreign Key:**  
  This links one table to another. It’s a column that refers to the primary key of a different table. It’s how we create relationships between tables.

- **Composite Key:**  
  Sometimes, we need more than one column to uniquely identify a record. That’s when we use a composite key, which is made of more than one attribute.

- **Alternate Key:**  
  These are other candidate keys that weren’t chosen as the primary key. They can still identify records uniquely.

- **Surrogate Key:**  
  A surrogate key is like a random ID, usually a number that’s generated by the system. It doesn’t really have any real-world meaning but serves as a unique identifier.

---

## **4. Mapping Cardinalities**

Cardinality just talks about how many instances of one thing relate to another thing. Here’s how it works:

- **One-to-One (1:1):**  
  One thing is linked to exactly one other thing. For example, one "Person" might have one "Passport".

- **One-to-Many (1:M):**  
  One thing is linked to many other things. For example, one "Department" can have many "Employees".

- **Many-to-One (M:1):**  
  Many things are linked to one thing. For example, many "Employees" work in one "Department".

- **Many-to-Many (M:N):**  
  Many things are linked to many other things. For example, many "Students" take many "Courses".

---

## **5. Entity Sets**

An entity set is just a collection of similar things (like "Students" or "Employees"). Here’s a breakdown:

- **Strong Entity Set:**  
  These can stand alone and have a primary key. For example, "Employee" can exist independently with an "Employee ID".

- **Weak Entity Set:**  
  These can’t stand alone and rely on a strong entity set for identification. For example, a "Dependent" might rely on an "Employee" to exist.

- **Entity Instance:**  
  This is just a specific example of an entity. For instance, "John Doe" is an entity instance of the "Employee" entity.

---

## **6. Relationship Sets**

Relationship sets are just how we link entities together. The types are:

- **Unary Relationship:**  
  This is when an entity is related to itself. For example, an "Employee" might manage other "Employees".

- **Binary Relationship:**  
  A relationship between two entities. For example, a "Student" might enroll in a "Course".

- **Ternary Relationship:**  
  A relationship involving three entities. For example, a "Project" might involve an "Employee" and a "Department".

- **N-ary Relationship:**  
  A relationship involving more than three entities.

---

## **7. E-R Diagram (Entity-Relationship Diagram)**

E-R diagrams are like maps for your database. They help you see how everything is connected. Here’s how the components look:

- **Rectangles:** Represent entity sets.
- **Ellipses:** Represent attributes.
- **Diamonds:** Represent relationships.
- **Lines:** Connect entities, attributes, and relationships.
- **Double Rectangles:** Represent weak entity sets.

---

## **8. Weak Entity Sets**

A weak entity set can’t exist on its own. It relies on a strong entity for identification. For example, an "Order Item" relies on an "Order" entity to exist.

---

## **9. Strong Entity Sets**

A strong entity set has a primary key and doesn’t rely on anything else. For example, an "Employee" has a unique "Employee ID" and can exist without needing other entities.

---

That’s it! These notes should help you get a solid understanding of database concepts. If anything’s unclear or you want to dive deeper into any of these topics, just let me know!

---

