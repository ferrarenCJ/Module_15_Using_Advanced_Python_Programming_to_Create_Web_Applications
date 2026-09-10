# Video 15.1 – Introduction and Information

## Module Overview

Module 15 focuses on using advanced Python programming techniques to create web applications and build database-driven solutions.

This module includes three major project submissions:

1. Project 15.1 – Creating a Books Web Application
2. Project 15.2 Part 1 – Creating a Student Grades Database
3. Project 15.2 Part 2 – Redundant Dictionaries in Python

Estimated effort: approximately 15.5 hours.

---

# Learning Outcomes

Upon completion of this module, I will be able to:

- Create an application using web tokens.
- Describe applications of authorization servers.
- Create a relational database using Python.
- Implement redundant dictionaries in Python.

---

# Project 15.1: Creating a Books Web Application

## Objective

Build a web application that displays a collection of books while implementing authentication and authorization controls.

## Topics Covered

- JSON Web Tokens (JWT)
- Authentication
- Authorization
- Authorization Servers
- User Roles
- Role-Based Access Control (RBAC)
- Web Application Development
- Flask-based Web Applications
- Website Security

## Key Features

### Book Collection

- Display books on a website.
- Add book images.
- Manage book information.

### User Management

- Multiple users.
- Username/password authentication.
- Secure login process.

### Authorization

Different users can have different permissions:

#### Admin

- Create books
- Update books
- Delete books
- Manage users

#### Reader

- View books
- Search books

---

# Project 15.2 Part 1: Student Grades Database

## Objective

Create a grading database using Python data structures.

## Concepts Used

### Lists

Store:

- Students
- Assignments
- Grades

### Dictionaries

Store:

- Student records
- Grade records
- Assignment information

### Functions

Perform:

- Data entry
- Data retrieval
- Grade calculations

### Relational Database Concepts

Relationships:

Student → Problem Sets

Student → Grades

Problem Set → Weight

## Final Goal

Calculate weighted averages for students using a database built entirely in Python.

---

# Project 15.2 Part 2: Redundant Dictionaries

## Objective

Improve the student grades database by implementing redundant dictionaries.

## Benefits of Redundant Dictionaries

- Faster lookups
- Better performance
- Reduced search time
- Improved database efficiency

## Concepts Covered

- Dictionary indexing
- Hash-based lookups
- Data redundancy for performance
- Advanced Python functions

---

# Key Python Topics

## Data Structures

### Lists

```python
students = []