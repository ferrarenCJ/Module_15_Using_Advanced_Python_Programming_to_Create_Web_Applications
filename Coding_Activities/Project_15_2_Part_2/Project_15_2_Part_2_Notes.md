# Required Project 15.2 (Part 2): Redundant Dictionaries in Python

## Objective

Enhance the student grades database developed in Part 1 by implementing redundant dictionaries to improve lookup performance and support weighted grade calculations.

---

# Key Concepts

## Redundant Dictionaries

A redundant dictionary stores the same data in multiple dictionary structures to provide multiple lookup paths.

Benefits:

- Faster data retrieval
- Direct access by ID or Name
- Direct access by Student or Problem Set
- Reduced searching and traversal

Trade-Offs:

- Increased memory usage
- More complex updates
- Multiple structures must remain synchronized

---

# Helper Functions

## get()

Retrieves a value from a dictionary by key.

```python
def get(dict, key):
    if key in dict:
        return dict[key]
    else:
        return None
```

---

## get2()

Retrieves a value from a nested dictionary.

```python
def get2(dict1, key1, key2):
    dict2 = get(dict1, key1)

    if dict2:
        return get(dict2, key2)
    else:
        return None
```

---

## add2()

Adds a value to a nested dictionary.

```python
def add2(db, key1, key2, value):
    if key1 not in db:
        db[key1] = {}

    db[key1][key2] = value
```

---

# Question 1

## Define an Empty Redundant Dictionary

```python
def empty():
    return {
        "studentsById": {},
        "studentsByName": {},
        "psets": {},
        "gradesByStudent": {},
        "gradesByPset": {}
    }
```

### Initialize Database

```python
db = empty()
```

---

# Question 2

## Add Student

Stores student information in two lookup structures.

```python
def addStudent(db, student_id, student_name):
    db["studentsById"][student_id] = student_name
    db["studentsByName"][student_name] = student_id
```

### Example

```python
addStudent(db, 1, "Alice")
```

Results:

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

---

# Question 3

## Lookup Student Name by ID

```python
def studentNameFromId(db, student_id):
    return get(db["studentsById"], student_id)
```

### Example

```python
studentNameFromId(db, 1)
```

Output:

```python
"Alice"
```

---

# Question 4

## Lookup Problem Set Points

```python
def psetPointsFromId(db, pset_id):
    return get(db["psets"], pset_id)
```

### Example

```python
psetPointsFromId(db, 2)
```

Output:

```python
20
```

---

# Question 5

## Add Grade

Stores grade information redundantly.

```python
def addGrade(db, student_id, pset_id, points):
    add2(db["gradesByStudent"], student_id, pset_id, points)
    add2(db["gradesByPset"], pset_id, student_id, points)
```

### Example

```python
addGrade(db, 1, 2, 18)
```

Results:

```python
gradesByStudent = {
    1: {
        2: 18
    }
}
```

and

```python
gradesByPset = {
    2: {
        1: 18
    }
}
```

---

# Question 6

## Grade on a Specific Problem Set

```python
def gradeOn(db, student_id, pset_id):
    return get2(db["gradesByStudent"], student_id, pset_id)
```

### Example

```python
gradeOn(db, 1, 2)
```

Output:

```python
18
```

---

# Question 7

## View All Grades on a Problem Set

Returns student names and grades.

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

### Example

Input:

```python
{
    1: 10,
    2: 18,
    3: 25
}
```

Output:

```python
{
    "Alice": 10,
    "Bob": 18,
    "Charlie": 25
}
```

---

# Weighted Grade Functions

## gradeOnWeighted()

```python
def gradeOnWeighted(db, student_id, pset_id, pset_points):
    grade = gradeOn(db, student_id, pset_id)

    if grade == None:
        return 0
    else:
        return grade / pset_points
```

---

# Question 8

## Calculate All Weighted Grades for a Student

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

### Example

Output:

```python
[1.0, 0.9, 0.8333]
```

---

## Calculate Final Grade

```python
def finalGradeOf(db, student_id):
    grades = studentGradesWeighted(db, student_id)

    return round(
        sum(grades) / len(grades) * 100,
        1
    )
```

---

# Question 9

## Generate Final Grades Report

```python
def finalGrades(db):
    return [
        {
            "id": student_id,
            "name": student_name,
            "grade": finalGradeOf(db, student_id)
        }
        for student_id, student_name
        in db["studentsById"].items()
    ]
```

---

# Sample Data

```python
addStudent(db, 1, "Alice")
addStudent(db, 2, "Bob")
addStudent(db, 3, "Charlie")

addPset(db, 1, 10)
addPset(db, 2, 20)
addPset(db, 3, 30)

addGrade(db, 1, 1, 10)
addGrade(db, 1, 2, 18)
addGrade(db, 1, 3, 25)

addGrade(db, 2, 3, 15)

addGrade(db, 3, 3, 10)
```

---

# Expected Final Output

```python
print(finalGrades(db))
```

Output:

```python
[
    {
        'id': 1,
        'name': 'Alice',
        'grade': 91.1
    },
    {
        'id': 2,
        'name': 'Bob',
        'grade': 16.7
    },
    {
        'id': 3,
        'name': 'Charlie',
        'grade': 11.1
    }
]
```

---

# Final Database Structure

```python
{
    "studentsById": {
        1: "Alice",
        2: "Bob",
        3: "Charlie"
    },

    "studentsByName": {
        "Alice": 1,
        "Bob": 2,
        "Charlie": 3
    },

    "psets": {
        1: 10,
        2: 20,
        3: 30
    },

    "gradesByStudent": {
        1: {
            1: 10,
            2: 18,
            3: 25
        },
        2: {
            3: 15
        },
        3: {
            3: 10
        }
    },

    "gradesByPset": {
        1: {
            1: 10
        },
        2: {
            1: 18
        },
        3: {
            1: 25,
            2: 15,
            3: 10
        }
    }
}
```

---

# Key Takeaways

- Redundant dictionaries intentionally duplicate data structures.
- Multiple access paths improve lookup performance.
- Helper functions simplify working with nested dictionaries.
- `add2()` allows efficient updates to nested dictionaries.
- Dictionary comprehensions can transform data during retrieval.
- List comprehensions simplify weighted grade calculations.
- Redundant dictionaries demonstrate concepts similar to database indexing and denormalized reporting structures used in data engineering.