# Self-Study Knowledge Check 15.3: Redundant Dictionaries in Python

## Score

Completed Successfully

Questions: 6

Result: 6/6 Correct

---

## Key Concepts

### What is a Redundant Dictionary?

A redundant dictionary stores the same information in multiple dictionary structures to provide multiple access paths to the data.

Example:

```python
grades_by_student = {
    1: {1: 98, 2: 108}
}

grades_by_pset = {
    1: {1: 98},
    2: {1: 108}
}
```

The data is duplicated intentionally to improve lookup performance.

---

## Benefits

### Fast Access

Dictionary lookups are generally O(1).

Redundant dictionaries allow data to be accessed through multiple lookup paths without performing additional searches.

Example:

```python
grades_by_student[1]
grades_by_pset[2]
```

---

## Creating a Blank Redundant Dictionary

```python
def empty():
    return {
        "column1": {},
        "column2": {}
    }

db = empty()
```

---

## Adding Data

Helper functions are commonly used.

Example:

```python
def addStudentDict(db, student_id, student_name):
    db["students"][student_id] = student_name
```

---

## Helper Functions

Redundant dictionaries often require custom helper functions for:

- Insert
- Update
- Delete
- Search
- Reporting

Examples:

```python
addStudentDict()
addPsetDict()
addGradeDict()
studentGrades()
gradeOnWeighted()
```

---

## Key Takeaways

- Redundant dictionaries improve performance.
- Data may be stored in multiple locations.
- Helper functions simplify maintenance.
- Dictionary lookups are typically O(1).
- The required functions depend on the dictionary structure.
- Redundancy trades memory for speed.

---

## Data Engineering Relevance

Redundant dictionaries demonstrate concepts that later appear in:

- Database indexes
- Caching
- Data warehouses
- Star schemas
- Denormalized reporting tables
- Analytics platforms

A common principle:

> Duplicate data strategically to optimize access patterns and query performance.