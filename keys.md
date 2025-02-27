# Key Types in Database Design

In database design, keys play a crucial role in uniquely identifying records or entities. There are several types of keys, each serving a specific purpose. The primary ones are **Primary Key**, **Super Key**, and **Candidate Key**. Below is a detailed explanation of each.

## 1. Super Key:
- A **Super Key** is a set of one or more attributes (columns) that can uniquely identify a record in a table.
- **Super Key** can have extra attributes that are not needed to uniquely identify the entity. In other words, any combination of attributes that ensures uniqueness in a table is a super key.
- It is not necessarily minimal; it can contain redundant attributes that don’t contribute to the uniqueness.

### Example:
Consider the following table of **Students**:

| Student ID | Name       | Email                |
|------------|------------|----------------------|
| 1          | John Doe   | john@example.com     |
| 2          | Jane Smith | jane@example.com     |

A **super key** could be:
- **{Student ID, Name}**
- **{Student ID, Email}**
- **{Student ID, Name, Email}**

Even though **{Student ID}** is sufficient to identify a student uniquely, the combinations of more attributes (e.g., **{Student ID, Name}**) are still considered super keys.

## 2. Candidate Key:
- A **Candidate Key** is a minimal super key, meaning it is the smallest set of attributes that uniquely identifies a record.
- It does not contain any unnecessary attributes. If any attribute is removed, it will no longer be able to uniquely identify the record.
- There can be multiple candidate keys for a table.

### Example:
From the previous **Students** table, **Student ID** is a **candidate key** because it can uniquely identify a student, and it is a minimal set. 

- **{Student ID}** is a candidate key.
- **{Email}** could also be a candidate key if no two students have the same email address.

In this case, both **Student ID** and **Email** are candidate keys because they uniquely identify each student, and no attribute is redundant.

## 3. Primary Key:
- The **Primary Key** is a special candidate key that is selected to uniquely identify records in a table.
- There can only be one primary key in a table.
- The primary key cannot have **NULL** values, and it must always contain unique values for each record.
- It is chosen from among the candidate keys, typically the one that is simplest and most efficient.

### Example:
In the **Students** table, if we choose **Student ID** as the primary key, it will look like this:

| **Student ID** | Name       | Email                |
|----------------|------------|----------------------|
| 1              | John Doe   | john@example.com     |
| 2              | Jane Smith | jane@example.com     |

Here, **Student ID** becomes the **primary key**, and it is selected from the available candidate keys.

## 4. Minimal Super Key:
- A **Minimal Super Key** is another way of referring to a **Candidate Key**. It is the smallest super key that can uniquely identify a record.
- It is "minimal" in the sense that no attribute can be removed without losing the uniqueness property.

### Example:
In the **Students** table:
- **{Student ID}** is a minimal super key.
- **{Email}** can also be a minimal super key if no two students have the same email.

## Relationships between these Keys:
1. **Super Key > Candidate Key > Primary Key:**
   - Every candidate key is a super key, but not every super key is a candidate key.
   - A primary key is chosen from the candidate keys.
   - A super key may include extra, unnecessary attributes (making it non-minimal), while a candidate key has no such redundancy.
   
2. **Example of hierarchy in keys:**
   Consider a table with the following attributes:
   - **Student ID**
   - **Email**
   - **Phone Number**

   Let's say:
   - **Super Keys**: **{Student ID}**, **{Email}**, **{Student ID, Name}**, **{Phone Number}**
   - **Candidate Keys**: **{Student ID}**, **{Email}**
   - **Primary Key**: **{Student ID}**

## Summary of Key Characteristics:

| **Key Type**        | **Uniqueness**                           | **Minimization**                          | **Example**                         |
|---------------------|------------------------------------------|-------------------------------------------|-------------------------------------|
| **Super Key**       | Uniquely identifies records              | Can have redundant attributes             | {Student ID, Name}                 |
| **Candidate Key**   | Uniquely identifies records              | Minimal, no redundant attributes          | {Student ID}, {Email}              |
| **Primary Key**     | Uniquely identifies records              | Minimal, selected from candidate keys     | {Student ID}                       |
| **Minimal Super Key** | Uniquely identifies records             | Minimal super key, equivalent to candidate key | {Student ID}, {Email}              |

## Conclusion:
- **Super Keys** are broad and can have redundant attributes.
- **Candidate Keys** are the minimal set of super keys.
- **Primary Key** is one chosen candidate key used to uniquely identify a record in the table, ensuring that values are not NULL and remain unique.

These keys are fundamental concepts in the relational database model, as they ensure data integrity and make it possible to manage and retrieve records efficiently.

