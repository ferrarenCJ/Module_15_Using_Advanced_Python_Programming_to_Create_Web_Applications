# Module 15 Cheat Sheet: Advanced Python Programming for Web Applications

## JWT Authentication Concepts

### Authentication

Verifies who a user is.

```text
Username + Password
```

### Authorization

Determines what a user can do after authentication.

Examples:

- Read Data
- Create Records
- Update Records
- Delete Records

---

## JSON Web Token (JWT)

### Structure

```text
Header.Payload.Signature
```

Example:

```text
xxxxx.yyyyy.zzzzz
```

### Common Claims

```json
{
  "user_id": 101,
  "username": "alice",
  "role": "admin"
}
```

---

## OpenID Connect

Used to authenticate users and retrieve profile information.

```text
User Login
    ↓
Identity Provider
    ↓
JWT Issued
    ↓
Application Access
```

---

# Dictionary Fundamentals

## Create Dictionary

```python
student = {
    "id": 1,
    "name": "Alice"
}
```

## Access Values

```python
student["name"]
```

Output:

```python
"Alice"
```

## Add Values

```python
student["grade"] = 95
```

---

# Nested Dictionaries

## Example

```python
grades = {
    1: {
        1: 90,
        2: 85
    }
}
```

Access:

```python
grades[1][2]
```

Output:

```python
85
```

---

# Redundant Dictionaries

## Purpose

Store the same information in multiple structures for faster access.

### Lookup by ID

```python
studentsById = {
    1: "Alice"
}
```

### Lookup by Name

```python
studentsByName = {
    "Alice": 1
}
```

Benefits:

- Faster lookups
- Multiple access paths
- Improved performance

---

# Helper Functions

## get()

```python
def get(dict, key):
    if key in dict:
        return dict[key]
    else:
        return None
```

---

## get2()

```python
def get2(dict1, key1, key2):
    dict2 = get(dict1, key1)

    if dict2:
        return get(dict2, key2)

    return None
```

---

## add2()

```python
def add2(db, key1, key2, value):

    if key1 not in db:
        db[key1] = {}

    db[key1][key2] = value
```

---

# List Comprehensions

## Syntax

```python
[
    expression
    for item in iterable
]
```

Example:

```python
[x * 2 for x in range(5)]
```

Output:

```python
[0, 2, 4, 6, 8]
```

---

# Dictionary Comprehensions

## Syntax

```python
{
    key: value
    for item in iterable
}
```

Example:

```python
{
    x: x*2
    for x in range(5)
}
```

Output:

```python
{
    0: 0,
    1: 2,
    2: 4,
    3: 6,
    *: 8
}
``*

*--

# Student Grades Database

## *atabase Structure

```python
{
   *"studentsById": {},
    "studentsB*Name": {},
    "*sets": {},
    "gradesByStudent": *},
    "gradesByPset": {}
}
```

-*-

## Add Student

```python**ddStudent(
    db,
    *,
    "Alice"
)
```

*--

## Add Problem Set

```python
*ddPset(
    db,
    *,
    10
)
```

---

## Add Grade
*```python*addGrade(
    db,
    1,
    1,
  * 10
)
```

*--

# Weighted Grades

## Formula
*```python*grade / pset_points
```

Example:
*```python
18 / 20
```

Output:

``*python
0.90
```

*quivalent:

```text
90%
```

---

* Final Grade Formula

```python
ro*nd(
    sum*grades)
    / len(grades)
    **100,
*   1
)
```

*--

# Module 15 Key Takeaways

✅ A*thentication vs Authorization

✅ J*T Fundamentals

✅ OpenID Connect

* Nested Dictionaries

✅ Redundant *ictionaries

✅ Helper Functions

✅*Dictionary Comprehensions

✅ List *omprehensions

✅ Weighted Grade Ca*culations

✅ Database Modeling

✅ *erformance Optimization Through Mu*tiple Lookup Paths