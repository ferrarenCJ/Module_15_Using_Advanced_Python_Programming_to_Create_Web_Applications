# Module 15: Wrap-Up

## Module Overview

In Module 15, two major projects were completed that expanded knowledge of Python programming, authentication, authorization, dictionaries, and data structures used in database design.

The module focused on building application security and developing efficient database structures using standard and redundant dictionaries.

---

# Learning Outcomes

By the end of this module, you should be able to:

- Implement authentication and authorization using JSON Web Tokens (JWT)
- Control application access based on user permissions
- Create and manage dictionary-based databases
- Use nested dictionaries
- Implement redundant dictionaries
- Apply list comprehensions
- Apply dictionary comprehensions
- Calculate weighted averages
- Build efficient lookup structures for data retrieval

---

# Project 15.1

## Authentication and Authorization

Project 15.1 focused on securing applications using JSON Web Tokens (JWTs).

### Topics Covered

- Authentication
- Authorization
- User login workflows
- Secure API access
- Token validation
- Permission management

### Key Concepts

#### Authentication

Authentication verifies who a user is.

Example:

```text
Username + Password
```

Result:

```text
User identity confirmed
```

---

#### Authorization

Authorization determines what an authenticated user is allowed to do.

Examples:

- View data
- Update records
- Delete records
- Access restricted areas

---

#### JSON Web Tokens (JWT)

JWTs provide a secure method for transmitting authentication information between systems.

Typical Workflow:

```text
User Login
      ↓
JWT Generated
      ↓
JWT Returned
      ↓
JWT Sent with Requests
      ↓
Access Granted or Denied
```

---

# Project 15.2 Part 1

## Creating a Student Grades Database

Part 1 introduced a simple database built using:

- Lists
- Dictionaries
- Functions
- List Comprehensions
- Dictionary Comprehensions

### Database Components

#### Students

```python
{
    "id": 1,
    "name": "Alice"
}
```

#### Problem Sets

```python
{
    "id": 1,
    "points": 100
}
```

#### Grades

```python
{
    "student": 1,
    "pset": 1,
    "points": 90
}
```

---

### Key Functions

```python
addStudent()
addPset()
addGrade()
getGrade()
getGradeDict()
```

---

### Skills Developed

- Data modeling
- Data storage
- Record retrieval
- List comprehension usage
- Dictionary comprehension usage

---

# Project 15.2 Part 2

## Redundant Dictionaries

Part 2 improved the student database by introducing redundant dictionaries.

### Purpose

Store the same information in multiple structures to provide faster access paths.

---

## Redundant Student Lookup

### Student ID to Name

```python
studentsById = {
    1: "Alice"
}
```

---

### Student Name to ID

```python
studentsByName = {
    "Alice": 1
}
```

---

## Redundant Grade Lookup

### Grades by Student

```python
gradesByStudent = {
    1: {
        1: 10,
        2: 18
    }
}
```

---

### Grades by Problem Set

```python
gradesByPset = {
    1: {
        1: 10
    },
    2: {
        1: 18
    }
}
```

---

## Benefits of Redundant Dictionaries

### Faster Access

Data can be retrieved directly using multiple lookup paths.

### Reduced Searching

No need to scan entire datasets to find records.

### Better Performance

Lookup operations remain efficient as data volumes increase.

### Improved Scalability

Supports larger datasets and more complex applications.

---

# Python Techniques Used Throughout Module 15

## Functions

Reusable blocks of code.

Example:

```python
def addStudent(db, student_id, student_name):
    pass
```

---

## Nested Dictionaries

Example:

```python
{
    1: {
        2: 18
    }
}
```

---

## List Comprehensions

Example:

```python
[
    gradeOnWeighted(
        db,
        student_id,
        pset_id,
        pset_points
    )
    for pset_id, pset_points
    in db["psets"].items()
]
```

---

## Dictionary Comprehensions

Example:

```python
{
    studentNameFromId(db, student_id): points
    for student_id, points in students.items()
}
```

---

# Connection to Data Engineering

The concepts introduced in this module directly relate to modern data engineering practices.

Examples include:

- Database indexing
- Data warehouse design
- Denormalized reporting tables
- Lookup dimension tables
- Caching systems
- Analytics platforms

---

# Key Takeaways

- Authentication verifies identity.
- Authorization controls access permissions.
- JSON Web Tokens provide secure authentication mechanisms.
- Dictionaries provide efficient key-value storage.
- Nested dictionaries support complex data relationships.
- Redundant dictionaries improve performance through multiple lookup paths.
- List comprehensions simplify data processing.
- Dictionary comprehensions simplify data transformations.
- Database design involves balancing storage efficiency and retrieval speed.
- The concepts learned in this module form a foundation for advanced data engineering and web application development.

---

# Module 15 Summary

### Project 15.1

✅ Authentication and Authorization using JWT

### Project 15.2 Part 1

✅ Student Grades Database using Lists and Dictionaries

### Project 15.2 Part 2

✅ Student Grades Database using Redundant Dictionaries

### Overall Skills Developed

✅ Authentication

✅ Authorization

✅ Data Modeling

✅ Dictionary-Based Databases

✅ Nested Dictionaries

✅ Redundant Dictionaries

✅ List Comprehensions

✅ Dictionary Comprehensions

✅ Weighted Grade Calculations

✅ Database Design Concepts