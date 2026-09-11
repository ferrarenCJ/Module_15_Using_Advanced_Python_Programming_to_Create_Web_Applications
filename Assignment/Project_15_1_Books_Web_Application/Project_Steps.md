# Project 15.1 - Creating a Books Web Application

## Objective

Develop a secure Books Web Application using JWT authentication and authorization.

The application will:

- Display a collection of books
- Support multiple users
- Authenticate users
- Authorize users based on roles
- Restrict access to protected resources

---

# Phase 1: Environment Setup

## Step 1: Create Project Folder

```text
Project_15_1_Books_Web_Application
│
├── app.py
├── users.py
├── books.py
├── requirements.txt
├── static
│   └── images
├── templates
└── README.md
```

---

## Step 2: Create Virtual Environment

```bash
python -m venv venv
```

Activate environment:

### Windows

```bash
venv\Scripts\activate
```

### Linux/Mac

```bash
source venv/bin/activate
```

---

## Step 3: Install Required Libraries

```bash
pip install flask
pip install flask-jwt
pip install pyjwt
```

Export requirements:

```bash
pip freeze > requirements.txt
```

---

# Phase 2: Create the Books Database

## Step 4: Create Book Data Structure

Each book should contain:

```python
{
    "id": 1,
    "title": "Python Basics",
    "author": "John Smith",
    "genre": "Programming",
    "image": "python.jpg"
}
```

---

## Step 5: Create Initial Book Collection

Add multiple books.

Example:

```python
books = [
    {...},
    {...},
    {...}
]
```

Minimum recommendation:

```text
5–10 books
```

---

## Step 6: Add Book Images

Store images inside:

```text
static/images
```

Examples:

```text
python.jpg
flask.jpg
data_engineering.jpg
aws.jpg
sql.jpg
```

---

# Phase 3: Create User Database

## Step 7: Create Users

Example users:

```python
users = [
    {
        "username": "reader",
        "password": "reader123",
        "role": "reader"
    },
    {
        "username": "admin",
        "password": "admin123",
        "role": "admin"
    }
]
```

---

## Step 8: Define User Roles

### Reader

Permissions:

```text
View Books
Search Books
```

---

### Admin

Permissions:

```text
View Books
Add Books
Update Books
Delete Books
Manage Users
```

---

# Phase 4: Implement Authentication

## Step 9: Create Login Endpoint

Example route:

```python
/login
```

Purpose:

```text
Receive username/password
```

---

## Step 10: Validate Credentials

Check:

```python
username
password
```

against user database.

---

## Step 11: Generate JWT

If login succeeds:

Create token containing:

```python
{
    "username": username,
    "role": role
}
```

---

## Step 12: Return JWT

Response:

```json
{
    "token": "JWT_TOKEN"
}
```

---

# Phase 5: Protect Routes

## Step 13: Create Protected Route

Example:

```python
/books
```

Require JWT to access.

---

## Step 14: Validate JWT

Verify:

- Signature
- User
- Expiration
- Permissions

---

## Step 15: Reject Invalid Tokens

Examples:

```text
Missing Token
Expired Token
Modified Token
```

Return:

```text
401 Unauthorized
```

---

# Phase 6: Book Viewing Features

## Step 16: Display All Books

Reader and Admin should be able to:

```text
View Books
```

Example page:

```text
Books Collection
---------------
Book 1
Book 2
Book 3
```

---

## Step 17: Display Book Images

Each record should show:

```text
Title
Author
Image
Genre
```

---

## Step 18: Search Books

Allow searching by:

```text
Title
Author
Genre
```

---

# Phase 7: Admin Features

## Step 19: Add New Books

Admin only.

Fields:

```text
Title
Author
Genre
Image
```

---

## Step 20: Edit Books

Admin only.

Update:

```text
Title
Author
Genre
```

---

## Step 21: Delete Books

Admin only.

Remove book from collection.

---

# Phase 8: Authorization

## Step 22: Enforce Reader Permissions

Reader can:

✅ View

✅ Search

Reader cannot:

❌ Add

❌ Edit

❌ Delete

---

## Step 23: Enforce Admin Permissions

Admin can:

✅ View

✅ Search

✅ Add

✅ Edit

✅ Delete

---

# Phase 9: Security Testing

## Step 24: Test Reader Account

Verify:

```text
Reader can view books.
Reader cannot modify books.
```

---

## Step 25: Test Admin Account

Verify:

```text
Admin can perform all actions.
```

---

## Step 26: Test JWT Validation

Verify:

```text
Valid JWT → Access Granted

Invalid JWT → Access Denied

Expired JWT → Access Denied
```

---

# Phase 10: Final Review

## Step 27: Review Application

Verify:

- Users authenticate correctly
- JWT tokens generated correctly
- JWT validation works
- Reader restrictions work
- Admin permissions work
- Books display correctly
- Images load correctly

---

## Step 28: Capture Screenshots

Take screenshots of:

```text
Login Page

Reader View

Admin View

Books List

JWT Authentication

Role-Based Access Example
```

Save under:

```text
Screenshots/
```

---

## Step 29: Final Documentation

Update:

```text
README.md
Notes.md
Project_Steps.md
```

Document:

- Architecture
- Authentication Flow
- Authorization Flow
- Lessons Learned

---

# Deliverables Checklist

- [ ] Flask application created
- [ ] User database created
- [ ] Book database created
- [ ] JWT authentication implemented
- [ ] Authorization implemented
- [ ] Reader role implemented
- [ ] Admin role implemented
- [ ] Book search implemented
- [ ] Book add/update/delete implemented
- [ ] Screenshots captured
- [ ] Documentation completed
- [ ] Project submitted