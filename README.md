# Module 15: Using Advanced Python Programming to Create Web Applications

## Overview

Module 15 focused on applying advanced Python programming concepts to web application development and database design.

Topics covered include:

- Authentication and Authorization
- JSON Web Tokens (JWT)
- OpenID Connect
- Python Dictionaries
- Nested Dictionaries
- Redundant Dictionaries
- List Comprehensions
- Dictionary Comprehensions
- Database Modeling
- Weighted Grade Calculations
- Flask Web Applications

---

## Learning Outcomes

By completing this module, I learned how to:

- Implement authentication and authorization mechanisms.
- Work with JSON Web Tokens (JWTs).
- Build secure web applications.
- Design dictionary-based databases in Python.
- Implement nested and redundant dictionary structures.
- Use list and dictionary comprehensions efficiently.
- Calculate weighted grades using reusable helper functions.
- Optimize data retrieval through multiple lookup paths.

---

## Folder Structure

```text
Module_15_Using_Advanced_Python_Programming_to_Create_Web_Applications/
│
├── Assignment/
│
├── Cheat_Sheets/
│   ├── Flask_Cheat_Sheet.md
│   ├── Module_15_Python_Web_Applications_Cheat_Sheet.md
│   ├── Python_Dictionaries_Cheat_Sheet.md
│   └── Relational_Database_Cheat_Sheet.md
│
├── Coding_Activities/
│   ├── Project_15_1_Creating_A_Books_Web_Application/
│   │
│   ├── Project_15_2_Part_1/
│   │   ├── Required_Project_15.2_Part_1-Creating_a_Student_Grades_Database.ipynb
│   │   └── Project_15_2_Part_1_Notes.md
│   │
│   └── Project_15_2_Part_2/
│       ├── Required_Project_15.2_Part_2-Redundant_Dictionaries_in_Python.ipynb
│       └── Project_15_2_Part_2_Notes.md
│
├── Discussions/
│   └── Self_Study_Discussion_15_1_Thinking_Like_A_Data_Scientist/
│       └── Self_Study_Discussion_15_1.md
│
├── Knowledge_Checks/
│   └── Self_Study_Knowledge_Check_15_3_Redundant_Dictionaries/
│       └── Self_Study_Knowledge_Check_15_3_Redundant_Dictionaries.md
│
├── Resources/
│   ├── Module_15_Glossary/
│   │   └── Module_15_Glossary.md
│   │
│   ├── Module_15_Wrap_Up/
│   │   └── Module_15_Wrap_Up_Notes.md
│   │
│   ├── Solution_Files/
│   │   ├── Module_15_Solution_Files.md
│   │   ├── Project 15.1_Creating a Books Web Application.pdf
│   │   ├── Required_Project_15.2_Part_1_solution.zip
│   │   └── Required_Project_15.2_Part_2_solution.zip
│   │
│   └── Video_Transcripts/
│
├── Sandbox/
├── Videos/
├── README.md
└── requirements.txt
```

---

## Cheat Sheets

### Flask Cheat Sheet

Topics Covered:

- Flask fundamentals
- Application structure
- Routing
- Templates
- Web APIs
- Authentication and Authorization

### Python Dictionaries Cheat Sheet

Topics Covered:

- Dictionary creation
- Dictionary methods
- Nested dictionaries
- Key-value lookups
- Dictionary operations

### Relational Database Cheat Sheet

Topics Covered:

- Primary Keys
- Foreign Keys
- Relationships
- Normalization
- Database design fundamentals

### Module 15 Python Web Applications Cheat Sheet

Topics Covered:

- JWT Authentication
- OpenID Connect
- Nested Dictionaries
- Redundant Dictionaries
- List Comprehensions
- Dictionary Comprehensions
- Weighted Grade Calculations

---

## Videos Completed

### Video 15.9: Redundant Dictionaries in Python Exercise

Topics:

- Redundant dictionaries
- Nested dictionary structures
- Data retrieval optimization
- Multiple lookup paths

### Video 15.10: Redundant Dictionaries in Python Solution

Topics:

- Dictionary comprehensions
- List comprehensions
- Student grade reporting
- Weighted grade calculations
- Efficient database design

---

## Projects Completed

### Project 15.1: Creating a Books Web Application

Topics Covered:

- JWT Authentication
- Authorization
- Flask Web Applications
- User Management
- Secure API Design

Skills Gained:

- Authentication workflows
- Authorization controls
- Secure API access
- User validation

---

### Project 15.2 Part 1: Creating a Student Grades Database

Topics Covered:

- Python Lists
- Dictionaries
- Functions
- List Comprehensions
- Dictionary Comprehensions

Key Functionality:

- Add students
- Add problem sets
- Add grades
- Retrieve grades
- Generate grade reports

---

### Project 15.2 Part 2: Redundant Dictionaries in Python

Topics Covered:

- Redundant Dictionaries
- Nested Dictionaries
- Helper Functions
- Database Optimization
- Weighted Grade Calculations

Key Functionality:

- Lookup students by ID
- Lookup students by name
- Lookup grades by student
- Lookup grades by assignment
- Generate weighted grade reports

---

## Knowledge Checks Completed

### Self-Study Knowledge Check 15.3: Redundant Dictionaries in Python

Topics Reviewed:

- Redundant dictionary initialization
- Helper functions
- Dictionary manipulation
- Data retrieval
- Performance benefits

Status:

✅ Completed Successfully

---

## Discussions Completed

### Self-Study Discussion 15.1: Thinking Like a Data Scientist

Resource Shared:

- Python Documentation for List and Dictionary Comprehensions

Key Takeaway:

- Visualizing dictionary structures before coding simplifies implementation and debugging.

---

## Key Concepts Learned

### Authentication

Verifies a user's identity before granting access.

### Authorization

Determines what actions an authenticated user can perform.

### JSON Web Token (JWT)

A secure method for transmitting authentication and authorization information.

### OpenID Connect

An authentication layer built on top of OAuth 2.0 that provides identity verification.

### Nested Dictionaries

Dictionaries that contain other dictionaries as values.

Example:

```python
{
    1: {
        2: 18
    }
}
```

### Redundant Dictionaries

Store the same information in different structures to improve lookup performance.

Example:

```python
studentsById = {
    1: "Alice"
}

studentsByName = {
    "Alice": 1
}
```

### Dictionary Comprehensions

Create dictionaries concisely.

Example:

```python
{
    key: value
    for key, value in iterable
}
```

### List Comprehensions

Create lists concisely.

Example:

```python
[
    item
    for item in iterable
]
```

---

## Resources

### Module 15 Glossary

Topics:

- Claims
- JWT Payloads
- Serialized Tokens
- Deserialized Tokens
- OpenID Connect
- Redundant Dictionaries

### Module 15 Wrap-Up

Summary of:

- Authentication
- Authorization
- Student database projects
- Redundant dictionary implementations

### Solution Files

Included solutions for:

- Project 15.1
- Project 15.2 Part 1
- Project 15.2 Part 2

---

## Module 15 Takeaways

- Authentication verifies identity.
- Authorization controls access.
- JWTs provide secure user validation.
- Flask can be used to build secure web applications.
- Dictionaries are powerful database-like structures.
- Nested dictionaries model relationships efficiently.
- Redundant dictionaries improve lookup speed.
- Comprehensions make code more concise and readable.
- Helper functions improve maintainability and reusability.
- Database design requires balancing simplicity, flexibility, and performance.

---

## Portfolio Skills Demonstrated

- Python Programming
- Flask Development
- JWT Authentication
- Authorization
- OpenID Connect
- Data Modeling
- Database Design
- Nested Dictionaries
- Redundant Dictionaries
- List Comprehensions
- Dictionary Comprehensions
- Data Retrieval Optimization
- Weighted Grade Analytics

---

## Status

✅ Module 15 Complete

**Course:** MIT Professional Education - Applied Data Science Program  
**Module:** 15  
**Focus:** Advanced Python Programming for Web Applications and Database Design