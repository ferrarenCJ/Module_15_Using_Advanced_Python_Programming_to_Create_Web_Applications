# Project 15.1 Notes

## Project Goal

Create a secure web application that manages a collection of books and uses JWT authentication and authorization to control user access.

---

# Application Requirements

## Books

The application should support:

- Book title
- Author
- Genre
- Description
- Cover image

---

## Users

The application should support multiple users.

Example users:

| Username | Role |
|-----------|--------|
| reader1 | Reader |
| reader2 | Reader |
| admin1 | Admin |
| admin2 | Admin |

---

# Authentication Workflow

## Step 1

User logs in.

```text
Username
Password
```

---

## Step 2

Authorization server validates credentials.

---

## Step 3

JWT is generated.

```text
Header.Payload.Signature
```

---

## Step 4

JWT returned to user.

---

## Step 5

User sends HTTP requests containing JWT.

---

## Step 6

Application server validates JWT.

---

# Authorization

## Reader

Allowed:

- View books
- Search books

Not allowed:

- Create books
- Delete books
- Manage users

---

## Admin

Allowed:

- View books
- Create books
- Modify books
- Delete books
- Manage users

---

# JWT Notes

JWT stands for:

```text
JSON Web Token
```

Components:

```text
Header
Payload
Signature
```

Payload contains:

```text
Claims
```

Example claims:

```json
{
  "userId": "12345",
  "role": "admin"
}
```

---

# Key Concepts

## Authentication

Who are you?

---

## Authorization

What are you allowed to do?

---

## Claims

Information stored in the JWT payload.

---

## Secret Key

Shared between:

- Authorization Server
- Application Server

Used to validate JWTs.

---

# Testing Checklist

- [ ] User login works
- [ ] JWT generated correctly
- [ ] JWT validation works
- [ ] Reader role restricted
- [ ] Admin role has full access
- [ ] Book images display
- [ ] Unauthorized access prevented
- [ ] Application functions correctly

---

# Personal Notes

## Challenges

-

## Lessons Learned

-

## Improvements

-

## Additional Features

-
