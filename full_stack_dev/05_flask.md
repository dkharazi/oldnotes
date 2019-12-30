## General Description
- Flask is a lightweight WSGI web application framework
- WSGI is to Python what Servlets are to Java
- Specifically, it is a common specification for web servers that allows different web servers and application frameworks to interact based on a common API
- Flask is designed to make getting started quick and easy, with the ability to scale up to complex applications
- It began as a simple wrapper around Werkzeug and Jinja and has become one of the most popular Python web application frameworks

## Routing
- Modern web applications use meaningful URLs to help users
- Users are more likely to like a page and come back if the page uses a meaningful URL they can remember and use to directly visit a page
- Use the route() decorator to bind a function to a URL
```
@app.route('/')
def index():
    return 'Index Page'

@app.route('/hello')
def hello():
    return 'Hello, World'
```

## Variable Rules
- You can add variable sections to a URL by marking sections with <variable_name>
- Your function then receives the <variable_name> as a keyword argument
- Optionally, you can use a converter to specify the type of the argument like <converter:variable_name>
```
@app.route('/user/<username>')
def show_user_profile(username):
    # show the user profile for that user
    return 'User %s' % escape(username)

@app.route('/post/<int:post_id>')
def show_post(post_id):
    # show the post with the given id, the id is an integer
    return 'Post %d' % post_id

@app.route('/path/<path:subpath>')
def show_subpath(subpath):
    # show the subpath after /path/
    return 'Subpath %s' % escape(subpath)
```

## HTTP Methods
- Web applications use different HTTP methods when accessing URLs
- You should familiarize yourself with the HTTP methods as you work with Flask
- By default, a route only answers to GET requests
- You can use the methods argument of the route() decorator to handle different HTTP methods
```
from flask import request

@app.route('/login', methods=['GET', 'POST'])
def login():
    if request.method == 'POST':
        return do_the_login()
    else:
        return show_the_login_form()
```

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
- http://flask.palletsprojects.com/en/1.1.x/quickstart/#routing
- https://opensource.com/article/18/4/flask
- https://realpython.com/flask-by-example-part-1-project-setup/
- https://damyanon.net/post/flask-series-structure/
