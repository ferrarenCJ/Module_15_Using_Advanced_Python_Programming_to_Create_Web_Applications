# Video 15.2 – JSON Web Tokens (JWT) Architecture

## Overview

This video introduces the architecture and workflow behind JSON Web Tokens (JWT), which are commonly used to authenticate and authorize users in web applications.

JWT enables a system to:

- Verify user identity (Authentication)
- Control user permissions (Authorization)
- Securely transmit user information between systems
- Support role-based access control (RBAC)

Project 15.1 uses JWT to manage access to the Books Web Application.

---

# Key Concepts

## Authentication

Authentication answers the question:

> "Who are you?"

The user provides credentials, typically:

- Username
- Password

If the credentials are valid, the system verifies the user's identity.

Example:

```text
Username: admin
Password: password123