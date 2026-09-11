# Video 15.8: Creating a Student Grades Database Using Dictionaries (08:59)

## Overview

In this video, Dr. Williams demonstrates an alternative database design using dictionaries instead of lists.

This approach improves lookup performance and simplifies data retrieval.

---

## Dictionary-Based Design

Instead of storing student records in a list:

```python
students = [
    {"studentid": 1, "firstname": "John"}
]
```

Use a dictionary:

```python
students = {
    1: "John",
    2: "Mary"
}
```

---

## Direct Access

Dictionary keys provide direct access to records.

Example:

```python
students[1]
```

Output:

```text
John
```

---

## Benefits of Dictionaries

### Faster Retrieval

Instead of:

```python
for student in students:
```

Use:

```python
students[studentid]
```

---

### Simpler Code

Direct access eliminates the need for repeated loops.

---

### Better Performance

Dictionary lookups are generally faster than searching lists.

---

## Redundant Dictionaries

Additional dictionaries may be created to improve retrieval speed.

Examples:

```python
student_names
student_grades
problem_sets
```

Data may be stored in more than one structure to avoid repeated searches.

---

## Advantages

- Faster lookups
- Reduced search time
- Simpler query logic
- Better scalability

---

## Disadvantages

- Duplicate data
- Additional maintenance
- Increased complexity when updating records

---

## Key Takeaways

- Dictionaries provide efficient key-based access.
- Dictionary lookups are faster than list searches.
- Redundant dictionaries improve performance.
- Database design involves trade-offs between speed and complexity.
- Choosing the appropriate data structure is important for application performance.