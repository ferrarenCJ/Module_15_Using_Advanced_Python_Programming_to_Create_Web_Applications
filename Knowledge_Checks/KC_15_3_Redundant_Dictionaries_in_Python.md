# Self-Study Knowledge Check 15.3: Redundant Dictionaries in Python

## Learning Outcome

- Implement redundant dictionaries in Python.

---

## Question 1

### What is the main benefit of utilizing Python redundant dictionaries?

**Answer:** Fast access

### Explanation

Redundant dictionaries store the same data in multiple structures, allowing information to be accessed through different lookup paths. This improves performance and provides faster access to stored data.

---

## Question 2

### How would you write code to define and initialize a blank redundant dictionary with column names equal to `column1` and `column2`?

**Answer:**

```python
def empty():
    return {"column1": {}, "column2": {}}

db = empty()
```

### Explanation

A redundant dictionary is initialized by defining a function that returns a dictionary containing multiple nested dictionaries that will hold related data.

---

## Question 3

### Can you add keys and values to a redundant dictionary?

**Answer:** Yes, you can write a function to append keys and values to a dictionary.

### Explanation

Redundant dictionaries behave like normal Python dictionaries. Helper functions can be created to add and maintain data within the dictionary structure.

Example:

```python
def addStudentDict(db, student_id, student_name):
    db["students"][student_id] = student_name
```

---

## Question 4

### How can you add values to a redundant dictionary key?

**Answer:** You can write a helper function to add values to a redundant dictionary key.

### Explanation

Helper functions provide a controlled way to insert values into nested dictionary structures while maintaining consistency across the redundant data store.

---

## Question 5

### What operations and functions must be defined and called to define a redundant dictionary?

**Answer:** The operations and functions you will define and call will depend on the structure of the redundant dictionary that you want to create.

### Explanation

Different database designs require different helper functions. The specific functions depend on how the dictionary is organized and how the data will be accessed.

Examples include:

```python
empty()
addStudentDict()
addPsetDict()
addGradeDict()
```

---

## Question 6

### Are separate user-defined functions needed to perform different types of data manipulation on redundant dictionaries?

**Answer:** Yes, user-defined helper functions are needed to handle redundant dictionaries.

### Explanation

Separate helper functions are typically created for:

- Creating records
- Updating records
- Retrieving records
- Calculating values
- Managing nested dictionary structures

These functions simplify working with redundant dictionary-based databases.

---

## Key Concepts

### Redundant Dictionaries

A redundant dictionary stores information in multiple locations to optimize lookup speed.

### Benefits

- Faster data access
- Multiple lookup paths
- Improved performance
- Efficient retrieval

### Trade-Offs

- Increased memory usage
- Additional maintenance required
- Updates may need to be applied to multiple structures

### Common Helper Functions

```python
empty()
addStudentDict()
addPsetDict()
addGradeDict()
studentGrades()
gradeOnWeighted()
```

---

## Key Takeaways

- Redundant dictionaries improve lookup performance.
- Multiple dictionary structures may contain the same data.
- Helper functions are commonly used to manage redundant data.
- Dictionary lookups generally provide O(1) access time.
- The design of helper functions depends on the dictionary structure being implemented.
- Redundant dictionaries demonstrate concepts used in database indexing and high-performance data systems.