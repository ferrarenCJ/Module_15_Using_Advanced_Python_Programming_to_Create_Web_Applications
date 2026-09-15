# Relational Database Cheat Sheet

## Primary Key (PK)

Uniquely identifies a record.

Example:

```text
student_id
```

| student_id | name |
|------------|------|
| 1 | Alice |
| 2 | Bob |

---

## Foreign Key (FK)

References a primary key in another table.

Example:

```text
student_id
```

in a grades table.

---

## One-to-One Relationship

```text
Person
  ↔
Passport
```

---

## One-to-Many Relationship

```text
Student
   ↓
Grades
```

One student can have many grades.

---

## Many-to-Many Relationship

```text
Students
    ↕
Courses
```

Implemented through a bridge table.

---

## Entity

A real-world object represented as a table.

Examples:

- Students
- Employees
- Vehicles
- Orders

---

## Attribute

A column in a table.

Example:

```text
student_name
```

---

## Record

A row in a table.

Example:

```text
1 | Alice
```

---

## Normalization

Process of reducing redundancy.

Goals:

- Reduce duplication
- Improve consistency
- Improve data integrity

---

## Basic SQL

### Select

```sql
SELECT *
FROM STUDENTS;
```

### Filter

```sql
SELECT *
FROM STUDENTS
WHERE STUDENT_ID = 1;
```

### Join

```sql
SELECT *
FROM STUDENTS S
JOIN GRADES G
  ON S.STUDENT_ID = G.STUDENT_ID;
```

---

## Database Design Tips

- Use meaningful primary keys.
- Avoid duplicate data.
- Normalize data where appropriate.
- Create indexes on frequently searched columns.
- Use foreign keys to enforce relationships.

---

## Key Takeaways

- Tables store entities.
- Rows store records.
- Columns store attributes.
- Primary keys uniquely identify records.
- Foreign keys create relationships.
- Normalization reduces redundancy.