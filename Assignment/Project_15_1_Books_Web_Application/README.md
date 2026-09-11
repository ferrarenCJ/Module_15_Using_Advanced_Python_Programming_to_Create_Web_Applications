# Project 15.1 - Creating a Books Web Application

## Overview

Project 15.1 focuses on building a secure Books Web Application using Python, Flask, JSON Web Tokens (JWT), authentication, authorization, and role-based access control (RBAC).

The application allows users to:

- View a collection of books
- Authenticate using a username and password
- Receive a JWT after successful login
- Access protected resources
- View book cover images
- Add books based on assigned permissions

The project demonstrates how JWT authentication and authorization are implemented in modern web applications.

---

## Learning Outcome

Create an application using web tokens.

---

## Technologies Used

- Python
- Flask
- Flask-RESTful
- Flask-JWT-Extended
- HTML
- JWT Authentication
- Authorization Decorators
- VS Code

---

## Project Structure

```text
Project_15_1_Books_Web_Application
│
├── README.md
├── Notes.md
├── Screenshots
│
├── Source_Code
│   ├── app.py
│   ├── requirements.txt
│   ├── static
│   │   ├── image1.png
│   │   ├── image2.png
│   │   ├── image3.png
│   │   ├── image4.png
│   │   └── image5.png
│   │
│   └── templates
│       ├── addbook.html
│       ├── addimage.html
│       ├── books.html
│       ├── index.html
│       └── register.html
│
└── submission
```

---

## Features

### Authentication

Users log in using:

- Username
- Password

A JWT token is generated after successful authentication.

---

### Authorization

Role-based access control is implemented.

Supported roles:

- Admin
- Reader

---

### Admin Capabilities

Admin users can:

- View books
- Add books
- Upload book images

---

### Reader Capabilities

Reader users can:

- View books

Reader users cannot:

- Add books
- Upload images

---

## Books Added

The original starter application contained three books.

Additional books added during the project:

1. Fluent Python
2. Python Crash Course

---

## Additional Users Added

### Admin

```text
admin2
```

### Reader

```text
reader2
```

---

## Security Implementation

JWT authentication is implemented using:

```python
flask-jwt-extended
```

The application stores:

```text
Username
Role
```

inside JWT claims.

---

## Custom Authorization Decorator

The application uses:

```python
admin_required(fn)
```

to restrict access to administrative functions.

Only users with the role:

```text
admin
```

can:

- Add books
- Upload images

---

## Testing Results

### Admin User

Successfully:

- Logged in
- Viewed books
- Added books

---

### Reader User

Successfully:

- Logged in
- Viewed books

Access was denied when attempting administrative actions.

---

## Screenshots Collected

1. Flask-RESTful installation
2. Flask-JWT-Extended installation
3. Project opened in VS Code
4. Two books added
5. Cover image 1 uploaded
6. Cover image 2 uploaded
7. books.html updated
8. Users added
9. admin_required function
10. Localhost running
11. Homepage displayed
12. Admin login
13. Books page with images
14. Book added by admin
15. Reader login
16. Reader access denied

---

## Key Takeaways

- JWT provides secure authentication.
- Authorization controls access to protected resources.
- Flask decorators can enforce role-based security.
- Users can be assigned different permissions.
- Web applications commonly use JWT tokens for session management.
- RBAC improves application security and user management.