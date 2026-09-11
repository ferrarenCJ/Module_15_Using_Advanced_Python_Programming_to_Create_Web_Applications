# Project 15.2 (Part 1): Creating a Student Grades Database

## Overview

This project focused on building a student grading database using Python dictionaries, lists, functions, list comprehensions, and dictionary comprehensions.

The project progressed through two database designs:

1. List-based database
2. Dictionary-based database

---

# Part 1: List-Based Database

## Student Records

```python
s1 = {"id": 1, "name": "Alice"}
s2 = {"id": 2, "name": "Bob"}
s3 = {"id": 3, "name": "Fred"}
```

## Problem Set Records

```python
p1 = {"id": 1, "MaxScore": 100}
p2 = {"id": 2, "MaxScore": 80}
p3 = {"id": 3, "MaxScore": 90}
```

## Grade Records

```python
g1 = {"sid": 1, "pid": 1, "score": 90}
g2 = {"sid": 2, "pid": 1, "score": 95}
g3 = {"sid": 1, "pid": 2, "score": 50}
```

## Database Structure

```python
db = {
    "students": [],
    "psets": [],
    "grades": []
}
```

---

# Functions

## addStudent()

Adds a student dictionary to the database.

```python
def addStudent(db, studentID, studentName):
    db["students"].append({
        "id": studentID,
        "name": studentName
    })
```

## addPset()

Adds a problem set record.

```python
def addPset(db, pset_id, pset_total_points):
    db["psets"].append({
        "id": pset_id,
        "points": pset_total_points
    })
```

## addGrade()

Adds a grade record.

```python
def addGrade(db, student_id, pset_id, points):
    db["grades"].append({
        "student": student_id,
        "pset": pset_id,
        "points": points
    })
```

## getGrade()

Returns a list containing matching grade values.

```python
def getGrade(db, student_id, pset_id):
    return [
        row["points"]
        for row in db["grades"]
        if row["student"] == student_id
        and row["pset"] == pset_id
    ]
```

## getGradeDict()

Returns the grade using a dictionary comprehension.

```python
def getGradeDict(student_id, pset_id):
    return {
        "grade": row["points"]
        for row in db["grades"]
        if row["student"] == student_id
        and row["pset"] == pset_id
    }
```

---

# Part 2: Dictionary-Based Database

## Empty Database

```python
def empty():
    return {
        "students": {},
        "psets": {},
        "grades": {}
    }
```

Example:

```python
db_dict = empty()
```

---

## addStudentDict()

```python
def addStudentDict(db, student_id, student_name):
    db["students"][student_id] = student_name
```

## addPsetDict()

```python
def addPsetDict(db, pset_id, pset_total_points):
    db["psets"][pset_id] = pset_total_points
```

## addGradeDict()

```python
def addGradeDict(db, student_id, pset_id, points):
    if student_id not in db["grades"]:
        db["grades"][student_id] = {}

    db["grades"][student_id][pset_id] = points
```

Example Database:

```python
{
    "students": {
        1: "Alice",
        2: "Bob",
        3: "Charlie"
    },
    "psets": {
        1: 100,
        2: 120,
        3: 130
    },
    "grades": {
        1: {1:98, 2:108, 3:125},
        2: {3:115},
        3: {3:110}
    }
}
```

---

# Helper Functions

## studentGrades()

```python
def studentGrades(db, student_id):
    return get(db["grades"], student_id)
```

## gradeOn()

```python
def gradeOn(db, student_id, pset_id):
    return get2(db["grades"], student_id, pset_id)
```

## gradeOnWeighted()

```python
def gradeOnWeighted(db, student_id, pset_id, pset_points):
    grade = gradeOn(db, student_id, pset_id)

    if grade is None:
        return 0

    return grade / pset_points * 100
```

## studentGradesWeighted()

```python
def studentGradesWeighted(db, student_id):
    return [
        gradeOnWeighted(
            db,
            student_id,
            pset_id,
            pset_points
        )
        for pset_id, pset_points in db["psets"].items()
    ]
```

## finalGrades()

```python
def finalGrades(db):
    return [
        {
            "id": id,
            "name": name,
            "grade": finalGradeOf(db, id)
        }
        for id, name in db["students"].items()
    ]
```

---

# Key Concepts

- Dictionaries
- Nested Dictionaries
- Lists
- Functions
- List Comprehensions
- Dictionary Comprehensions
- Database Modeling
- Data Retrieval
- Weighted Grade Calculations
- Aggregation Logic

---

# Lessons Learned

- Dictionary lookups are faster than list searches.
- Nested dictionaries simplify grade retrieval.
- List comprehensions provide concise filtering.
- Dictionary comprehensions efficiently transform data.
- Normalized data structures improve scalability and maintainability.