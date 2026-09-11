# Video 15.10: Redundant Dictionaries in Python Solution

## Overview

In this video, Dr. Williams reviews the solution to the Redundant Dictionaries exercise and demonstrates how redundant dictionary structures can improve database performance by providing multiple lookup paths to the same information.

The lesson also reinforces the use of Python dictionary comprehensions to efficiently create new dictionary structures from existing data.

---

# Learning Objectives

After completing this video, you should be able to:

- Implement redundant dictionaries in Python
- Store data using multiple lookup paths
- Access student information efficiently
- Access grade information by student or by problem set
- Use dictionary comprehensions
- Use nested dictionaries
- Calculate weighted grades

---

# What Are Redundant Dictionaries?

A redundant dictionary stores the same information in multiple locations.

Example:

```python
{
    "studentsById": {
        1: "Alice"
    },

    "studentsByName": {
        "Alice": 1
    }
}
```

Both dictionaries contain the same information but support different access methods.

---

# Why Use Redundant Dictionaries?

## Lookup by Student ID

```python
db["studentsById"][1]
```

Output:

```python
"Alice"
```

---

## Lookup by Student Name

```python
db["studentsByName"]["Alice"]
```

Output:

```python
1
```

---

## Benefits

- Faster retrieval
- Direct access paths
- Reduced searching
- Improved scalability
- Better performance for large datasets

---

# Database Structure

The completed database contains several redundant dictionary structures.

```python
{
    "studentsById": {},
    "studentsByName": {},
    "psets": {},
    "gradesByStudent": {},
    "gradesByPset": {}
}
```

---

# Grade Storage

## Grades by Student

```python
{
    1: {
        1: 10,
        2: 18,
        3: 25
    }
}
```

Allows quick access to all grades for a specific student.

Example:

```python
db["gradesByStudent"][1]
```

Output:

```python
{
    1: 10,
    2: 18,
    3: 25
}
```

---

## Grades by Problem Set

```python
{
    3: {
        1: 25,
        2: 15,
        3: 10
    }
}
```

Allows quick access to all student grades for a specific assignment.

Example:

```python
db["gradesByPset"][3]
```

Output:

```python
{
    1: 25,
    2: 15,
    3: 10
}
```

---

# Dictionary Comprehensions

The video revisits dictionary comprehensions.

General Syntax:

```python
{
    key_expression: value_expression
    for item in iterable
}
```

---

## Example

```python
{
    studentNameFromId(db, student_id): points
    for student_id, points
    in students.items()
}
```

Result:

```python
{
    "Alice": 25,
    "Bob": 15,
    "Charlie": 10
}
```

---

# gradesOnPset()

Dictionary comprehension is used to convert student IDs into student names.

```python
def gradesOnPset(db, pset_id):
    students = get(db["gradesByPset"], pset_id)

    if students:
        return {
            studentNameFromId(db, student_id): points
            for student_id, points in students.items()
        }
    else:
        return {}
```

---

# Weighted Grades

The project calculates weighted grades by dividing earned points by available points.

Example:

```python
grade / pset_points
```

For example:

```python
18 / 20
```

Output:

```python
0.90
```

or

```python
90%
```

---

# List Comprehensions

The solution also uses list comprehensions to compute weighted grades.

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

# Final Grade Calculation

Student weighted grades are averaged.

```python
def finalGradeOf(db, student_id):
    grades = studentGradesWeighted(
        db,
        student_id
    )

    return round(
        sum(grades) / len(grades) * 100,
        1
    )
```

---

# Example Results

Student:

```python
Alice
```

Scores:

```python
10/10
18/20
25/30
```

Weighted values:

```python
1.0
0.9
0.8333
```

Final grade:

```python
91.1
```

---

# Final Report

The final report returns:

```python
[
    {
        "id": 1,
        "name": "Alice",
        "grade": 91.1
    },
    {
        "id": 2,
        "name": "Bob",
        "grade": 16.7
    },
    {
        "id": 3,
        "name": "Charlie",
        "grade": 11.1
    }
]
```

---

# Dictionary Comprehension Review

Dictionary comprehensions provide a concise way to create dictionaries.

Template:

```python
{
    key: value
    for item in iterable
}
```

Advantages:

- Cleaner code
- Fewer lines
- Improved readability
- Faster development

---

# Key Takeaways

- Redundant dictionaries intentionally duplicate data.
- Multiple lookup paths improve performance.
- Student information can be accessed by ID or name.
- Grade information can be accessed by student or assignment.
- Dictionary comprehensions simplify dictionary creation.
- List comprehensions simplify calculations.
- Weighted grades can be calculated efficiently using reusable helper functions.
- Redundant dictionaries demonstrate concepts similar to database indexing and denormalized data structures used in data engineering.