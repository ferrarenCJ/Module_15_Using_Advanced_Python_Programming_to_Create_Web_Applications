# Project 15.1 - Creating a Books Web Application

## Objective

Build a secure Books Web Application using Flask and JSON Web Tokens (JWT) that supports authentication, authorization, role-based access control, book management, and book cover images.

---

# Project Workflow

## Step 1 - Install Flask Dependencies

Activate the Module 15 virtual environment.

Install Flask-RESTful:

```bash
pip install flask-restful
```

Install Flask-JWT-Extended:

```bash
pip install flask-jwt-extended
```

Verify successful installation.

### Screenshot

- Flask-RESTful installation
- Flask-JWT-Extended installation

---

# Step 2 - Open Project in VS Code

Open:

```text
Project_15_1_Books_Web_Application
```

Verify all project folders are visible.

### Screenshot

Project folder opened in VS Code.

---

# Step 3 - Review Starter Application

Review:

```text
app.py
templates/
static/
```

Understand:

- Books collection
- Users collection
- Authentication flow
- Authorization flow

---

# Step 4 - Add Additional Books

Locate:

```python
books = [
```

Add two additional books.

### Added Books

```python
{
    "id": 4,
    "author": "Luciano Ramalho",
    "country": "Brazil",
    "language": "English",
    "title": "Fluent Python",
    "year": 2022,
},
{
    "id": 5,
    "author": "Eric Matthes",
    "country": "USA",
    "language": "English",
    "title": "Python Crash Course",
    "year": 2023,
}
```

### Screenshot

Books list showing both new books.

---

# Step 5 - Add Cover Images

Copy two new cover images into:

```text
static/
```

### Added Images

```text
image4.png
image5.png
```

### Screenshot

Open image4.png in VS Code.

### Screenshot

Open image5.png in VS Code.

---

# Step 6 - Update books.html

Open:

```text
templates/books.html
```

Add image display logic.

### Added HTML

```html
/static/image{{book['id']}}.png
```

This dynamically displays the cover image associated with each book.

### Screenshot

Updated books.html file.

---

# Step 7 - Add Additional Users

Locate:

```python
users = [
```

Add:

```python
{"username": "admin2", "password": "admin2", "role": "admin"},
{"username": "reader2", "password": "reader2", "role": "reader"}
```

### Screenshot

Updated users list.

---

# Step 8 - Define Authorization Function

Create custom authorization decorator:

```python
def admin_required(fn):
    @wraps(fn)
    def wrapper(*args, **kwargs):
        claims = get_jwt()

        if claims.get("role") != "admin":
            return "Access Denied. Admin privileges required.", 403

        return fn(*args, **kwargs)

    return wrapper
```

Purpose:

- Restrict administrative functions
- Verify user role
- Enforce role-based access control

### Screenshot

admin_required function.

---

# Step 9 - Fix Authentication Logic

Update JWT claims.

### Original

```python
validUser["roles"]
```

### Updated

```python
validUser["role"]
```

---

Update JWT creation method.

### Updated

```python
access_token = create_access_token(
    identity=username,
    additional_claims=user_claims
)
```

---

# Step 10 - Run Application

Navigate to source folder.

```bash
cd Source_Code
```

Start application.

```bash
python app.py
```

Verify:

```text
Running on http://127.0.0.1:5000
```

### Screenshot

Terminal showing localhost connection.

---

# Step 11 - Open Application

Open:

```text
http://localhost:5000
```

Verify login page loads.

### Screenshot

Homepage displayed.

---

# Step 12 - Login as Admin

Login credentials:

```text
Username: testuser
Password: testuser
```

or

```text
Username: admin2
Password: admin2
```

Verify successful login.

### Screenshot

Admin login success.

---

# Step 13 - Verify Books Page

Navigate to:

```text
Books
```

Verify:

- Lean Startup
- A Seat at the Table
- Lean Thinking
- Fluent Python
- Python Crash Course

Verify all associated images display correctly.

### Screenshot

Books page with all cover images.

---

# Step 14 - Add New Book

Navigate to:

```text
Add Book
```

Add:

```text
Author: Ferraren
Title: Data Engineering on AWS
```

Submit form.

Verify book appears in collection.

### Screenshot

Book successfully added.

---

# Step 15 - Login as Reader

Logout.

Login using:

```text
Username: reader2
Password: reader2
```

Verify successful login.

### Screenshot

Reader login success.

---

# Step 16 - Test Authorization

While logged in as reader:

Navigate to:

```text
Add Book
```

Expected result:

```text
Access Denied. Admin privileges required.
```

Verify authorization enforcement.

### Screenshot

Reader access denied message.

---

# Testing Results

## Admin Testing

### Login

```text
Success
```

### View Books

```text
Success
```

### Add Book

```text
Success
```

---

## Reader Testing

### Login

```text
Success
```

### View Books

```text
Success
```

### Add Book

```text
Access Denied
```

---

# Security Features Implemented

## JWT Authentication

- Token generation
- Token validation
- Secure session handling

---

## Role-Based Access Control

Roles:

```text
Admin
Reader
```

Permissions are enforced through:

```python
admin_required()
```

---

# Project Enhancements

## Books Added

- Fluent Python
- Python Crash Course

---

## Images Added

- image4.png
- image5.png

---

## Users Added

### Admin

```text
admin2
```

### Reader

```text
reader2
```

---

# Deliverables Completed

- [x] Flask-RESTful Installed
- [x] Flask-JWT-Extended Installed
- [x] Project Opened in VS Code
- [x] Two Books Added
- [x] Two Cover Images Added
- [x] books.html Updated
- [x] Admin User Added
- [x] Reader User Added
- [x] admin_required Implemented
- [x] Application Running
- [x] Homepage Verified
- [x] Admin Login Verified
- [x] Books Display Verified
- [x] Book Addition Verified
- [x] Reader Login Verified
- [x] Reader Access Restricted
- [x] Screenshots Captured
- [x] Project Complete

---

# Key Takeaways

- JWT provides secure authentication services.
- Authorization determines what authenticated users may do.
- Role-based access control helps secure web applications.
- Flask decorators provide an efficient way to protect routes.
- JWT claims can store user roles and permissions.
- Modern web applications frequently use JWT authentication for session management.
- Administrative functionality should always be protected through authorization checks.