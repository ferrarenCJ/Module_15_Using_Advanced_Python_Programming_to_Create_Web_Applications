# Video 15.6: Creating a Database in Python (12:24)

## Overview

In this video, Dr. Williams demonstrates how to create a student grades database using Python lists, dictionaries, and functions.

The database stores:

- Students
- Problem Sets
- Grades

---

## Database Design

The database is divided into separate collections.

### Students

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

Example:

```python
{
    "psid": 1,
    "maxscore": 100
}
```

---

### Grades

Example:

```python
{
    "studentid": 1,
    "psid": 1,
    "score": 95
}
```

---

## Database Collections

Students:

```python
students = []
```

Problem Sets:

```python
problemsets = []
```

Grades:

```python
grades = []
```

---

## Functions

### addStudent()

Creates student records.

Example:

```python
addStudent(studentid, firstname, lastname)
```

---

### addProblemSet()

Creates assignment records.

Example:

```python
addProblemSet(psid, maxscore)
```

---

### addGrade()

Stores grades for students.

Example:

```python
addGrade(studentid, psid, score)
```

---

## Relationships

Records are linked using:

```text
studentid
psid
```

These identifiers connect:

```text
Students → Grades → Problem Sets
```

---

## Benefits

- Structured storage
- Reusable functions
- Consistent data entry
- Easy expansion

---

## Key Takeaways

- Lists can act like database tables.
- Dictionaries can represent database records.
- Functions simplify database maintenance.
- Shared identifiers create relationships between tables.