# Video 15.5: Relational Data Structures (03:06)

## Overview

In this video, Dr. Williams introduces relational data structures and explains different ways to organize student and grade information within a database.

The goal is to create relationships between students, assignments, and grades using Python data structures.

---

## Relational Data

Relational data consists of connected entities.

Example:

```text
Students
     ↓
Grades
     ↓
Problem Sets
```

Each student may have multiple grades, and each problem set may contain grades for multiple students.

---

## Main Entities

### Students

Store information about each student.

Example:

```python
{
    "studentid": 1,
    "firstname": "John",
    "lastname": "Smith"
}
```

---

### Problem Sets

Store assignment information.

Example:

```python
{
    "psid": 1,
    "maxscore": 100
}
```

---

### Grades

Store student scores.

Example:

```python
{
    "studentid": 1,
    "psid": 1,
    "score": 95
}
```

---

## Relationships

Relationships are established through shared keys.

Examples:

```text
studentid
psid
```

These values connect students, assignments, and grades together.

---

## Data Structure Options

### Lists

```python
students = []
```

---

### Dictionaries

```python
student = {
    "studentid": 1,
    "firstname": "John"
}
```

---

### Lists of Dictionaries

```python
students = [
    {"studentid": 1, "firstname": "John"},
    {"studentid": 2, "firstname": "Mary"}
]
```

---

## Benefits of Relational Structures

- Organized data storage
- Easier data retrieval
- Clear relationships between entities
- Simplifies database querying

---

## Key Takeaways

- Relational data contains connected records.
- IDs establish relationships between entities.
- Python lists and dictionaries can model relational databases.
- Good database design improves data retrieval and maintenance.