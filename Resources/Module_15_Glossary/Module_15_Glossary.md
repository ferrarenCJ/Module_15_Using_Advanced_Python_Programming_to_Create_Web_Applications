# Module 15: Glossary

## Claim

The data contained within the JWT payload is known as a claim.

Claims store information about a user or system and are used during authentication and authorization processes.

Example claims:

- User ID
- Username
- Role
- Permissions

---

## Deserialized Token

A deserialized token is one of the forms in which a JSON Web Token (JWT) can exist.

It contains:

- Header
- Payload

A deserialized token does not include the encoded string format used for transmission.

---

## OpenID Connect

OpenID Connect (OIDC) is an authentication protocol built on top of OAuth 2.0.

It allows web applications to:

- Authenticate users
- Verify user identity
- Obtain user profile information

OpenID Connect uses tokens issued by an authorization server to determine whether a user has been authenticated.

---

## Payload

The payload is the section of a JWT that contains user and system information.

Possible payload contents include:

- User ID
- Username
- Email Address
- IP Address
- User Roles
- System Metadata

Example:

```json
{
  "user_id": 123,
  "username": "alice",
  "role": "admin"
}
```

---

## Redundant Dictionary

A redundant dictionary is a dictionary structure that stores related information in multiple dictionary paths or collections.

Purpose:

- Improve lookup performance
- Provide multiple access paths
- Reduce search operations

Example:

```python
{
    "studentsById": {
        1: "Alice"
    },

    "studentsByName": {
        "Alice": 1
    }
}
```

In this example, the same information can be accessed by either student ID or student name.

---

## Serialized Token

A serialized token is the encoded form of a JWT that is transmitted between systems.

A serialized token contains:

- Header
- Payload
- Signature

Benefits:

- Secure data transfer
- Token verification
- Integrity checking
- Authentication support

Typical JWT Structure:

```text
header.payload.signature
```

Example:

```text
eyJhbGciOiJIUzI1NiIs...
```

---

# Module 15 Key Concepts

### Authentication

Verifying the identity of a user.

### Authorization

Determining what an authenticated user is allowed to do.

### JSON Web Token (JWT)

A secure token used to exchange authentication and authorization information.

### Dictionary Comprehension

A concise method for creating dictionaries.

Example:

```python
{
    key: value
    for key, value in iterable
}
```

### List Comprehension

A concise method for creating lists.

Example:

```python
[
    item
    for item in iterable
]
```

### Nested Dictionary

A dictionary that contains one or more dictionaries as values.

Example:

```python
{
    1: {
        2: 18
    }
}
```

### Weighted Grade

A grade calculated as a percentage of points earned relative to the total available points.

Example:

```python
18 / 20 = 0.90
```

Equivalent to:

```text
90%
```

---

# Module 15 Summary

Module 15 focused on:

- JWT Authentication
- Authorization
- OpenID Connect
- Dictionary-Based Databases
- Nested Dictionaries
- Redundant Dictionaries
- List Comprehensions
- Dictionary Comprehensions
- Student Grade Databases
- Weighted Grade Calculations

These concepts provide a foundation for building secure web applications and efficient data structures using Python.