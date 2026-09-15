# Flask Cheat Sheet

## Installation

```bash
pip install flask
```

---

## Import Flask

```python
from flask import Flask
```

---

## Create Application

```python
app = Flask(__name__)
```

---

## Basic Route

```python
@app.route('/')
def home():
    return "Hello World"
```

---

## Run Application

```python
if __name__ == "__main__":
    app.run(debug=True)
```

---

## Route Parameters

```python
@app.route('/user/<name>')
def user(name):
    return f"Hello {name}"
```

---

## Multiple HTTP Methods

```python
@app.route('/login', methods=['GET', 'POST'])
def login():
    pass
```

---

## Returning JSON

```python
from flask import jsonify

@app.route('/api')
def api():
    return jsonify({
        "status": "success"
    })
```

---

## Request Data

```python
from flask import request

username = request.form.get("username")
```

---

## Query Parameters

```python
name = request.args.get("name")
```

Example:

```python
/api?name=Alice
```

---

## Templates

```python
from flask import render_template

@app.route('/')
def home():
    return render_template("home.html")
```

---

## Redirects

```python
from flask import redirect

return redirect("/")
```

---

## Sessions

```python
from flask import session

session["user"] = "alice"
```

---

## JWT Authentication Flow

```text
Login
  ↓
JWT Created
  ↓
Client Stores Token
  ↓
Token Sent With Requests
  ↓
Access Granted
```

---

## Common Flask Commands

```bash
flask run
```

```bash
pip install flask
```

```bash
pip freeze > requirements.txt
```

---

## Key Takeaways

- Flask is a lightweight Python web framework.
- Routes define application endpoints.
- Templates separate logic from presentation.
- APIs often return JSON responses.
- JWTs are commonly used for authentication.