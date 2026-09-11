# Video 15.7: Querying a Database (04:40)

## Overview

In this video, Dr. Williams explains how to retrieve information from the student grades database using Python functions.

The focus is on obtaining grades for specific students and assignments.

---

## Database Queries

A query retrieves information from stored records.

Examples:

- Find a student
- Find a problem set
- Find a grade
- Calculate student performance

---

## Query Function

Example:

```python
getGrade(studentid, psid)
```

Purpose:

- Locate a student's grade
- Find a matching problem set
- Return the score

---

## Query Process

Step 1:

```text
Find Student
```

Step 2:

```text
Find Problem Set
```

Step 3:

```text
Find Matching Grade
```

Step 4:

```text
Return Score
```

---

## Searching Records

Typical logic:

```python
for grade in grades:
```

---

## Matching IDs

Example:

```python
if grade["studentid"] == studentid:
```

and

```python
if grade["psid"] == psid:
```

This ensures the correct grade is returned.

---

## Benefits of Query Functions

- Reusable logic
- Easier maintenance
- Consistent results
- Simplified reporting

---

## Key Takeaways

- Queries retrieve data from stored collections.
- Functions centralize retrieval logic.
- Shared IDs link records together.
- Querying data is one of the most important database operations.