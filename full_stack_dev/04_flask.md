## General Description
- Flask is a lightweight WSGI web application framework
- WSGI is to Python what Servlets are to Java
- Specifically, it is a common specification for web servers that allows different web servers and application frameworks to interact based on a common API
- Flask is designed to make getting started quick and easy, with the ability to scale up to complex applications
- It began as a simple wrapper around Werkzeug and Jinja and has become one of the most popular Python web application frameworks

## Example of Flask Application
```
from flask import Flask, escape, request

app = Flask(__name__)

@app.route('/')
def hello():
    name = request.args.get("name", "World")
    return f'Hello, {escape(name)}!'
```
```
$ env FLASK_APP=hello.py flask run
 * Serving Flask app "hello"
 * Running on http://127.0.0.1:5000/ (Press CTRL+C to quit)
```

## References
- https://blog.miguelgrinberg.com/post/the-flask-mega-tutorial-part-xv-a-better-application-structure
- https://opensource.com/article/18/4/flask
- https://realpython.com/flask-by-example-part-1-project-setup/
- https://damyanon.net/post/flask-series-structure/
