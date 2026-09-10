# Self-Study Knowledge Check 15.1: Authorization Servers

## Overview

- Due: September 17, 2026
- Points: 0
- Questions: 7
- Time Limit: None
- Attempts Allowed: Unlimited

### Learning Outcome Addressed

- Create an application using web tokens.

### Prompt

This knowledge check covered:

- JSON Web Tokens (JWT)
- Authentication
- Authorization
- Authorization Servers
- Application Servers
- JWT Payloads and Claims
- JWT Structure

---

# Question 1

## Question

When a user sends a login request to an authorization server, what kind of token is sent back to the user by the authorization server?

## Correct Answer

✅ JSON Web Token

### Explanation

When a user submits a username and password to an authorization server, the authorization server validates the credentials and returns a JSON Web Token (JWT). The JWT contains encrypted user information and privileges that will be used during future requests.

---

# Question 2

## Question

Which of the following is shared by the application server and authorization server?

## Correct Answer

✅ Secret Key

### Explanation

The application server and authorization server share a secret key used to encrypt, decrypt, sign, and validate JWTs. This shared secret allows both servers to verify token authenticity.

---

# Question 3

## Question

What does JWT stand for?

## Correct Answer

✅ JSON Web Token

### Explanation

JWT stands for JSON Web Token. JWTs are commonly used to authenticate and authorize users for web applications and APIs.

---

# Question 4

## Question

What kind of request does a user send to the application server during the authentication and authorization process?

## Correct Answer

✅ HTTP GET Request with JWT

### Explanation

After receiving a JWT from the authorization server, the user includes the token in requests to the application server. The application server validates the JWT before granting access to protected resources.

---

# Question 5

## Question

Where is the JWT inserted within the HTTP request for authorization?

## Correct Answer

✅ Header

### Explanation

The JWT is typically included in the HTTP Authorization header.

Example: