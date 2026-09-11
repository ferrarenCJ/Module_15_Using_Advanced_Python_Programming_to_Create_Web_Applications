# Video 15.9: Redundant Dictionaries in Python

## Overview

This lesson introduces the concept of **redundant dictionaries**.

A redundant dictionary design stores the same information in multiple dictionary structures. While this increases memory usage, it significantly improves lookup performance by providing multiple paths to access the same data.

## Why Use Redundant Dictionaries?

Without redundancy, finding data may require traversing multiple dictionaries or lists.

Example:

```python
student_name = db["students"][student_id]
grade = db["grades"][student_id][pset_id]
pset_points = db["psets"][pset_id]
```

As databases grow larger, repeated lookups can become expensive.

Redundant dictionaries provide alternative access paths that reduce lookup complexity.

---

## Traditional Database Structure

```python
db = {
    "students": {
        1: "Alice",
        2: "Bob"
    },

    "psets": {
        1: 100,
        2: 120
    },

    "grades": {
        1: {
            1: 98,
            2: 108
        },

        2: {
            2: 115
        }
    }
}
```

### Access Pattern

To retrieve Alice's score on Problem Set 2:

```python
db["grades"][1][2]
```

Result:

```python
108
```

---

## Redundant Dictionary Concept

Instead of storing information only once, create additional dictionaries that organize the same data differently.

Example:

```python
grades_by_student = {
    1: {1: 98, 2: 108},
    2: {2: 115}
}

grades_by_pset = {
    1: {1: 98},
    2: {1: 108, 2: 115}
}
```

The same grades exist in two locations.

Benefits:

- Faster lookups by student
- Faster lookups by assignment
- Less traversal
- Simpler queries

Tradeoff:

- More storage required
- Updates must occur in multiple locations

---

## Example

### Lookup by Student

```python
grades_by_student[1]
```

Output:

```python
{
    1: 98,
    2: 108
}
```

### Lookup by Problem Set

```python
grades_by_pset[2]
```

Output:

```python
{
    1: 108,
    2: 115
}
```

---

## Advantages

### Faster Retrieval

Direct dictionary access is:

```python
O(1)
```

on average.

### Multiple Navigation Paths

Data can be accessed:

- By Student
- By Assignment
- By Grade
- By Course

depending on the structure created.

### Improved Scalability

Large datasets benefit from avoiding repeated searches.

---

## Disadvantages

### Additional Memory Usage

The same data exists in multiple places.

Example:

```python
grade = 108
```

may be stored several times.

### More Complex Updates

Whenever a grade changes:

```python
grades_by_student[1][2] = 110
grades_by_pset[2][1] = 110
```

Both structures must be updated.

Failure to do so can create inconsistent data.

---

## Real-World Applications

Redundant dictionary structures are commonly used in:

- Database indexing
- Search engines
- Caching systems
- Analytics platforms
- Web applications
- Data engineering pipelines

Examples include:

- User lookup by ID
- Product lookup by SKU
- Customer lookup by account number
- Asset lookup by GIS identifier

---

## Key Takeaways

- Redundant dictionaries intentionally duplicate data.
- Redundancy improves lookup speed.
- Multiple dictionary structures provide different navigation paths.
- Dictionary lookups are generally O(1).
- Redundancy trades memory usage for performance.
- Data updates must keep all redundant structures synchronized.
- Similar concepts are used in database indexes and enterprise systems.

## MIT Pro Data Engineering Relevance

This lesson introduces a core data engineering principle:

**Store data in ways that optimize access patterns.**

The same concept appears later in:

- Database indexing
- Data warehousing
- Dimensional modeling
- Caching
- Distributed data systems
- High-performance analytics platforms