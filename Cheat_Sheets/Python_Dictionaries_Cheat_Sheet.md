# Python Dictionaries Cheat Sheet

## Create Dictionary

```python
student = {
    "id": 1,
    "name": "Alice"
}
```

---

## Access Values

```python
student["name"]
```

Output:

```python
Alice
```

---

## Add Values

```python
student["grade"] = 95
```

---

## Update Values

```python
student["grade"] = 100
```

---

## Remove Values

```python
del student["grade"]
```

---

## Get Value Safely

```python
student.get("grade")
```

---

## Dictionary Keys

```python
student.keys()
```

---

## Dictionary Values

```python
student.values()
```

---

## Dictionary Items

```python
student.items()
```

---

## Loop Through Dictionary

```python
for key, value in student.items():
    print(key, value)
```

---

## Nested Dictionary

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

---

## Dictionary Comprehension

```python
{
    x: x * 2
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
    4: 8
}
```

---

## Redundant Dictionary Example

```python
studentsById = {
    1: "Alice"
}

studentsByName = {
    "Alice": 1
}
```

Benefits:

- Faster lookups
- Multiple access paths
- Better performance

---

## Key Takeaways

- Dictionaries store key-value pairs.
- Keys must be unique.
- Dictionaries support O(1) lookups.
- Nested dictionaries support complex relationships.
- Dictionary comprehensions simplify data transformations.