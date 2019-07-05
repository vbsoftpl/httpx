# Advanced Usage

![Artwork by Kenneth Reitz](img/advanced.jpg)

## Client Instances

Using a Client instance to make requests will give you HTTP connection pooling,
provides cookie persistence, and allows you to apply configuration across
all outgoing requests.

```python
>>> client = requests3.Client()
>>> r = client.get('https://example.org/')
>>> r
<Response [200 OK]>
```

**TODO: Advanced Usage Documentation**

## Calling into Python Web Apps

You can configure a `requests3` client to call directly into a Python web
application, rather than making network requests.

This is particularly useful for two main use-cases:

* Using `requests3` as a client, inside test cases.
* Mocking out external services, during tests or in dev/staging environments.

Here's an example of integrating against a Flask application:

```python
from flask import Flask
import http3


app = Flask(__name__)

@app.route("/")
def hello():
    return "Hello World!"

client = requests3.Client(app=app)
r = client.get('http://example/')
assert r.status_code == 200
assert r.text == "Hello World!"
```

The application must expose either one of the [WSGI](https://www.python.org/dev/peps/pep-3333/) or [ASGI](https://asgi.readthedocs.io) protocol interfaces, which Requests can then call directly into.
