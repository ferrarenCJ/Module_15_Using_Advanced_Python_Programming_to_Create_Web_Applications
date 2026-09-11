# Video 15.4: Project 1 - Creating a Books Web Application Solution (08:02)

## Overview

In this video, Dr. Williams demonstrates the completed Books Web Application and explains how authentication, authorization, JWT tokens, user roles, and Flask decorators are used to secure the application.

---

## User Authentication

Users authenticate by providing a username and password.

After successful login:

- A JWT (JSON Web Token) is generated
- The user's identity is stored in the token
- The token is used to access protected routes

---

## User Roles

The application supports two user roles:

### Admin

Admin users can:

- View books
- Add books
- Upload book images

### Reader

Reader users can:

- View books

Reader users cannot:

- Add books
- Upload images

---

## Books Management

Books are stored in a Python list.

The application allows users to:

- View books
- Add books
- Display book details
- Display book cover images

Additional books can be added dynamically through the application.

---

## Book Cover Images

Book images are stored in the:

```text
static/
```

directory.

Images are associated with books using the book ID.

Example:

```html
/static/image{{book['id']}}.png
```

This allows the application to automatically display the correct cover image for each book.

---

## Authorization Using Decorators

The application uses a custom decorator to protect administrator-only functionality.

Example:

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

The decorator:

- Reads JWT claims
- Checks the user's role
- Grants access to administrators
- Denies access to non-administrators

---

## Protected Routes

Administrative routes are protected using:

```python
@jwt_required()
@admin_required
```

Examples include:

```text
/addbook
/addimage
```

Only authenticated administrators may access these routes.

---

## Admin Testing

Admin users can:

- Log in successfully
- View all books
- Add books
- Upload images

Example admin accounts:

```text
testuser
admin2
```

---

## Reader Testing

Reader users can:

- Log in successfully
- View books

Reader users cannot:

- Add books
- Upload images

When attempting administrative activities, the application displays:

```text
Access Denied. Admin privileges required.
```

---

## Key Takeaways

- JWT provides secure user authentication.
- Authorization controls access to protected resources.
- Role-based access control (RBAC) improves application security.
- Flask decorators provide an effective method for protecting routes.
- Admin and reader permissions can be managed through JWT claims.
- Static resources such as book images can be dynamically displayed using Jinja templates.
- Combining authentication and authorization creates a more secure web application.