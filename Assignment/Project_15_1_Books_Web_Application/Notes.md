# Project 15.1 Notes

## Project Summary

The goal of this project was to create a secure Books Web Application that uses JWT authentication and authorization to control access to application features.

The application supports multiple users and enforces different permissions based on assigned roles.

---

# Key Concepts

## Authentication

Authentication answers:

```text
Who are you?
```

Users submit:

- Username
- Password

The application verifies the credentials before granting access.

---

## Authorization

Authorization answers:

```text
What are you allowed to do?
```

Permissions are determined after authentication.

---

## JSON Web Tokens (JWT)

JWT stands for:

```text
JSON Web Token
```

JWTs are used to securely exchange information between:

- User
- Authorization Server
- Application Server

---

## JWT Structure

A serialized JWT consists of:

```text
Header
Payload
Signature
```

Example:

```text
Header.Payload.Signature
```

---

## Claims

A claim is data stored inside the JWT payload.

Examples:

```text
Username
Role
Permissions
Expiration Date
```

Example:

```json
{
  "username": "admin2",
  "role": "admin"
}
```

---

# User Roles

## Admin

Admin users can:

- View books
- Add books
- Upload images

Users:

```text
testuser
Anne
admin2
```

---

## Reader

Reader users can:

- View books

Reader users cannot:

- Add books
- Upload images

Users:

```text
John
reader2
```

---

# Admin Authorization Decorator

Custom decorator:

```python
def admin_required(fn):
```

Purpose:

- Verify JWT claims
- Confirm administrator privileges
- Restrict protected functionality

---

## Logic

```python
if claims.get("role") != "admin":
    return "Access Denied"
```

Only administrators are allowed to continue.

---

# Books Collection

## Original Books

1. Lean Startup
2. A Seat at the Table
3. Lean Thinking

---

## Added Books

4. Fluent Python
5. Python Crash Course

---

# Images

Cover images used:

```text
image1.png
image2.png
image3.png
image4.png
image5.png
```

Image display was implemented using:

```html
/static/image{{book['id']}}.png
```

---

# Testing Performed

## Admin Testing

### Login

```text
testuser
testuser
```

Result:

```text
Success
```

---

### Add Book

Result:

```text
Success
```

Added:

```text
Data Engineering on AWS
```

---

## Reader Testing

### Login

```text
reader2
reader2
```

Result:

```text
Success
```

---

### Add Book

Result:

```text
Access Denied. Admin privileges required.
```

Authorization successfully enforced.

---

# Lessons Learned

## Authentication vs Authorization

Authentication:

```text
Identity Verification
```

Authorization:

```text
Permission Verification
```

---

## JWT Benefits

- Stateless authentication
- Secure token exchange
- Easy role management
- Scalable web application design

---

## Flask Security

Flask decorators provide an effective mechanism for protecting routes and enforcing security policies.

---

# Personal Reflection

This project demonstrated how modern web applications implement authentication and authorization using JWT tokens. It also reinforced the importance of role-based access control and secure application design. The project provided hands-on experience with Flask, JWT configuration, decorators, HTML templates, and user management.