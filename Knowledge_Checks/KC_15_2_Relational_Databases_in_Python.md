# Self-Study Knowledge Check 15.2: Relational Databases in Python

## Question 1

### Which of the following can be used to represent a relational database in Python?

✅ Answer

```text
A dictionary of arrays
```

### Explanation

A relational database can be represented in Python using a dictionary containing arrays (lists) that act as tables.

Example:

```python
database = {
    "students": [],
    "grades": [],
    "problemsets": []
}
```

---

## Question 2

### Suppose you have created a database using a dictionary of arrays. The name of the dictionary is retail. There are three arrays within the retail dictionary: customer_details, order_details, and product_details. How would you add data to the product_details array in the retail dictionary?

✅ Answer

```python
retail['product_details'].append()
```

### Explanation

The syntax:

```python
retail['product_details']
```

accesses the `product_details` array within the `retail` dictionary.

To add new data to the array:

```python
retail['product_details'].append(new_product)
```

---

## Question 3

### What do you need to ensure when creating a relational database using Python?

✅ Answer

```text
That the entries in the tables are defined with a unique identifier.
```

### Explanation

Each record should contain a unique identifier so that records can be distinguished from one another and related across tables.

Example:

```python
{
    "studentid": 1001,
    "name": "John Smith"
}
```

The `studentid` uniquely identifies the record.

---

## Question 4

### Which of the following can be used to represent a database in Python?

✅ Answer

```text
All of the answer options are correct.
```

### Explanation

A database can be represented using various data structures, including:

#### Dictionary of Arrays

```python
database = {
    "students": [],
    "grades": []
}
```

#### Dictionary of Lists

```python
database = {
    "students": [],
    "courses": []
}
```

#### Dictionary of Dictionaries

```python
database = {
    1: {"name": "John"},
    2: {"name": "Mary"}
}
```

All of these approaches can be used to organize and store data.

---

## Question 5

### Suppose that you want to store student names and that there are duplicate student names in the data. Which field can you add to ensure that all the student records are unique?

✅ Answer

```text
StudentId
```

### Explanation

Student names are not guaranteed to be unique. A StudentId provides a unique identifier for each student.

Example:

```python
{
    "StudentId": 1001,
    "StudentName": "John Smith"
}
```

```python
{
    "StudentId": 1002,
    "StudentName": "John Smith"
}
```

Although the names are identical, the StudentId values make each record unique.

---

# Key Takeaways

- Relational databases in Python can be represented using a dictionary of arrays.
- Records should contain unique identifiers.
- Relationships are created using shared IDs.
- Arrays (lists) can be updated using `append()`.
- Databases in Python can be represented using dictionaries of arrays, lists, or dictionaries.
- StudentId is an example of a primary key used to uniquely identify records.