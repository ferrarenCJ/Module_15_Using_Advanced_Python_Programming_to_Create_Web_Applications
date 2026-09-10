# Video 15.3 – Project 1: Creating a Books Web Application

## Video Information

- Module: 15
- Video: 15.3
- Title: Project 1: Creating a Books Web Application
- Duration: 06:52

---

# Overview

This video introduces Project 15.1, where a Books Web Application will be developed using Python and JSON Web Tokens (JWT).

The project expands upon concepts introduced earlier in the program and adds:

- User authentication
- User authorization
- Role-based access control
- JWT security
- Book management functionality

Dr. Williams demonstrates some capabilities of the JWT library and encourages further exploration of the library documentation.

---

# Project Objective

Build a web application that:

- Displays a collection of books
- Supports multiple users
- Authenticates users with JWT
- Authorizes users based on roles
- Controls access to application features

---

# Key Technologies

## Python

Used to build the application logic.

### Responsibilities

- Business logic
- User handling
- Book management
- Authentication workflows

---

## JWT Library

The JWT library provides functionality for:

- Authentication
- Authorization
- Token generation
- Token validation
- Access control

The library simplifies the implementation of secure web applications.

---

# Authentication

Authentication determines:

```text
Who is the user?
```

Users provide credentials such as:

- Username
- Password

The server validates the credentials and issues a JWT.

---

## Authentication Flow

```text
User
  ↓
Username + Password
  ↓
Authorization Server
  ↓
Validate Credentials
  ↓
JWT Created
  ↓
Token Returned
```

---

# Authorization

Authorization determines:

```text
What is the user allowed to do?
```

Authorization occurs after authentication.

The application examines:

- User role
- Permissions
- Access level

before allowing an action.

---

# Role-Based Access Control (RBAC)

Project 15.1 will implement different permissions for different users.

## Reader Role

Typical permissions:

```text
View Books
Search Books
Browse Collection
```

---

## Admin Role

Typical permissions:

```text
View Books
Add Books
Edit Books
Delete Books
Manage Users
```

---

# Books Web Application Features

## Book Collection

The application stores information about books.

Possible attributes include:

- Title
- Author
- Genre
- Description
- Image

---

## Book Images

This project introduces image support.

Books can display:

- Cover images
- Thumbnails
- Visual previews

Images help improve the overall user experience.

---

## User Management

The application supports multiple users.

Each user can have:

```text
Username
Password
Role
Permissions
```

Examples:

```text
reader1
reader2
admin1
admin2
```

---

# JWT Library Capabilities

The JWT library provides tools to:

## Create Tokens

Generate JWTs after successful login.

Example concept:

```python
jwt.encode(payload, secret_key)
```

---

## Verify Tokens

Ensure incoming tokens are valid.

Example concept:

```python
jwt.decode(token, secret_key)
```

---

## Store Claims

JWT payloads may contain:

- User ID
- Username
- Role
- Permissions

Example:

```json
{
    "user": "admin",
    "role": "admin"
}
```

---

## Secure Application Resources

The JWT library can restrict access to:

- Pages
- APIs
- Administrative functions

Only authorized users can access protected resources.

---

# Example Workflow

## Reader User

```text
Login
 ↓
Receive JWT
 ↓
View Books
 ↓
Search Books
```

Allowed.

---

## Reader Attempts Admin Action

```text
Login
 ↓
Receive JWT
 ↓
Delete Book
```

Denied.

Reason:

```text
Insufficient Permissions
```

---

## Admin User

```text
Login
 ↓
Receive JWT
 ↓
Add Book
 ↓
Edit Book
 ↓
Delete Book
```

Allowed.

---

# Security Benefits

JWT improves application security through:

## Authentication

Verifies identity.

---

## Authorization

Verifies permissions.

---

## Stateless Sessions

Servers do not need to store session information.

---

## Token Validation

Protects against unauthorized access.

---

# Connection to Previous Modules

This project builds upon concepts introduced earlier in the program.

### Module 11

- Client-Server Architecture
- Web Applications

### Module 12

- Database Concepts

### Module 13

- Data Movement

### Module 14

- Backend Development Concepts

### Module 15

- Authentication
- Authorization
- JWT Security
- Protected Web Applications

---

# Real-World Applications

JWT authentication is commonly used in:

- Banking applications
- E-commerce platforms
- Social media websites
- Cloud platforms
- REST APIs
- Enterprise applications

Examples include:

```text
Amazon
Microsoft
Google
GitHub
Netflix
```

---

# Portfolio Relevance

Project 15.1 demonstrates several valuable skills:

## Web Development

- Application design
- User management
- Authentication

## Security

- JWT implementation
- Authorization
- Access control

## Python Development

- Backend programming
- Library integration
- Application architecture

## Data Engineering Relevance

Understanding authentication and authorization is important when working with:

- APIs
- Data platforms
- Cloud services
- Enterprise applications

---

# Key Terms

| Term | Definition |
|--------|------------|
| JWT | JSON Web Token |
| Authentication | Verifying user identity |
| Authorization | Determining permissions |
| RBAC | Role-Based Access Control |
| Claim | Information stored inside a JWT payload |
| Reader | User with limited permissions |
| Admin | User with elevated permissions |
| Token Validation | Process of verifying a JWT |

---

# Important Takeaways

- Project 15.1 introduces JWT authentication and authorization.
- The application will manage a collection of books.
- Different users will have different permissions.
- JWTs are used to control access to application resources.
- Admin users have elevated privileges.
- Reader users have limited privileges.
- The JWT library simplifies authentication and authorization implementation.
- This project creates a portfolio-ready secure web application.

---

# Personal Notes

## Key Concepts to Review

- [ ] JWT Architecture
- [ ] Authentication vs Authorization
- [ ] Role-Based Access Control (RBAC)
- [ ] JWT Payloads and Claims
- [ ] Token Validation
- [ ] Admin vs Reader Permissions
- [ ] Books Web Application Requirements

## Questions

- How are JWT tokens generated?
- How are JWT tokens validated?
- What claims should be stored in the payload?
- How should permissions be managed for different roles?
- What additional functionality could be added to the Books Web Application?