# Self-Study Knowledge Check 15.1: Authorization Servers

## Overview

- **Due:** September 17, 2026
- **Points:** 0
- **Questions:** 7
- **Time Limit:** None
- **Allowed Attempts:** Unlimited

## Learning Outcome Addressed

- Create an application using web tokens.

## Prompt

In this section, you were introduced to Project 15.1 and learned about JSON Web Tokens (JWTs), authentication, authorization, authorization servers, and application servers. This knowledge check tested your understanding of how JWTs are created, transmitted, and validated during the authentication and authorization process.

---

# Question 1

## Question

When a user sends a login request to an authorization server, what kind of token is sent back to the user by the authorization server?

## Correct Answer

✅ JSON Web Token

## Explanation

When a user submits a username and password to an authorization server, the authorization server authenticates the credentials and returns a JSON Web Token (JWT).

The JWT contains encrypted information such as:

- Username
- User privileges
- User role
- Authorization claims

The user then includes the JWT in future requests to access protected resources.

---

# Question 2

## Question

Which of the following is shared by the application server and authorization server?

## Correct Answer

✅ Secret Key

## Explanation

The application server and authorization server share a secret key that is used to:

- Encrypt JWTs
- Sign JWTs
- Verify JWT signatures
- Validate token authenticity

Without the shared secret key, the application server would be unable to verify whether the JWT was issued by a trusted authorization server.

---

# Question 3

## Question

What does JWT stand for?

## Correct Answer

✅ JSON Web Token

## Explanation

JWT stands for:

```text
JSON Web Token
```

JWTs are widely used in modern web applications for:

- Authentication
- Authorization
- Secure exchange of user information

After login, a JWT becomes proof that a user has been authenticated.

---

# Question 4

## Question

What kind of request does a user send to the application server during the authentication and authorization process?

## Correct Answer

✅ HTTP GET Request with JWT

## Explanation

After receiving a JWT from the authorization server, the user sends requests to the application server that include the JWT.

Example process:

```text
User Logs In
        ↓
Authorization Server
        ↓
JWT Generated
        ↓
User Receives JWT
        ↓
HTTP GET Request + JWT
        ↓
Application Server
```

The application server validates the JWT before granting access to the requested resource.

---

# Question 5

## Question

Where is the JWT inserted within the HTTP request for authorization?

## Correct Answer

✅ Header

## Explanation

The JWT is typically stored within the HTTP Authorization Header.

Example:

```http
Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...
```

When the application server receives the request, it extracts the JWT from the header and validates it.

---

# Question 6

## Question

What is the term for the data within the JWT payload?

## Correct Answer

✅ Claim

## Explanation

The information stored inside the JWT payload is called a claim.

Examples of claims include:

- User ID
- Username
- Role
- Issuer
- Expiration Date
- Permissions

Example payload:

```json
{
    "userId": "1234567-abc",
    "role": "admin",
    "exp": "20261231"
}
```

Each field inside the payload is considered a claim.

---

# Question 7

## Question

What fields is a serialized web token composed of?

## Correct Answer

✅ Header, Payload, and Signature

## Explanation

A serialized JWT contains three sections:

### Header

Contains metadata about the token.

Example:

```json
{
    "typ": "JWT",
    "alg": "HS256"
}
```

### Payload

Contains claims and user information.

Example:

```json
{
    "userId": "1234567-abc",
    "name": "bob",
    "admin": true
}
```

### Signature

Used to verify token integrity and authenticity.

The general JWT structure is:

```text
Header.Payload.Signature
```

Example:

```text
eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9
.
eyJ1c2VySWQiOiIxMjM0NTY3LWFiYyIsImFkbWluIjp0cnVlfQ
.
SflKxwRJSMeKKF2QT4fwpMeJf36POk6yJV_adQssw5c
```

---

# Summary

## Key Concepts

### Authentication

Authentication answers:

```text
Who are you?
```

This is typically accomplished using:

- Username
- Password
- JWT

---

### Authorization

Authorization answers:

```text
What are you allowed to do?
```

Examples:

- Reader role
- Admin role
- Editor role

---

### JWT Components

A serialized JWT contains:

```text
Header
Payload
Signature
```

---

### Claims

Claims are the pieces of information stored within the JWT payload.

Examples:

```text
User ID
Username
Role
Permissions
Expiration Date
```

---

### Secret Key

The shared secret key allows:

- JWT creation
- JWT signing
- JWT verification
- JWT validation

---

### JWT Request Flow

```text
User
 ↓
Login Request
 ↓
Authorization Server
 ↓
JWT Generated
 ↓
User Receives JWT
 ↓
HTTP Request + JWT
 ↓
Application Server
 ↓
JWT Validation
 ↓
Access Granted / Denied
```

---

# Key Takeaways

- JWT stands for JSON Web Token.
- Authorization servers create JWTs after successful authentication.
- Application servers validate JWTs before granting access.
- JWTs are typically stored in the HTTP Authorization Header.
- Information inside the payload is called a claim.
- Serialized JWTs contain Header, Payload, and Signature.
- Authorization servers and application servers share a secret key for token verification.
- JWTs are commonly used for authentication and authorization in modern web applications.