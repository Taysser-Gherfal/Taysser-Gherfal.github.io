## Intro to Flask

------

### Basic Application Structure

All Flask applications must create an application instance. The application instance is an object of class Flask.

```python
from flask import Flask
app = Flask(__name__)
```
Flask uses the __name__ argument to determine the location of the application, which in turn allows it to locate other files that are part of the application, such as images and templates.



### Routes and View Functions

The association between a URL and the function that handles it is called a route.

```Python
@app.route('/')
def index():
    return '<h1>Hello World!</h1>'
```

Flask also offers a more traditional way to set up the application routes with the app.add-url-rule() method

```Python
def index():
    return '<h1>Hello World!</h1>'
app.add_url_rule('/', 'index', index)
```

Functions like index() that handle application URLs are called view functions.

- #### A route with a dynamic component:


```Python
@app.route('/user/<name>')
def user(name): return '<h1>Hello, {}!</h1>'.format(name)
```



### A Complete Application

- An application instance and a single route and view function


```Python
from flask import Flask
app = Flask(__name__)

@app.route('/')
def index():
    return '<h1>Hello World!</h1>'
```

- An application with two routes and two view functions.


```Python
from flask import Flask 
app = Flask(__name__)

@app.route('/') 
def index(): 
    return '<h1>Hello World!</h1>'

@app.route('/user/<name>') 
def user(name): 
    return '<h1>Hello, {}!</h1>'.format(name)
```


### Starting the application

For Linux and macOS

```Bash
(venv) $ export FLASK_APP=hello.py 
(venv) $ flask run
```

For Windows 

```Bash
(venv) $ set FLASK_APP=hello.py 
(venv) $ flask run
```

Once the server starts up, it goes into a loop that accepts requests and services them. This loop continues until you stop the application by pressing **Ctrl+C**.

#### Listen for connections on the public network interface enabling other computers in the same network to connect as well:

```Bash
(venv) $ flask run --host 0.0.0.0
```

### Debug Mode

```Bash
(venv) $ export FLASK_APP=hello.py 
(venv) $ export FLASK_DEBUG=1 
(venv) $ flask run
```
+ Flask applications can optionally be executed in debug mode. 
+ In this mode, two very convenient modules of the development server called the reloader and the debugger are enabled by default.
+ When the reloader is enabled, Flask watches all the source code files of your project and automatically restarts the server when any of the files are modified.
+ The debugger is a web-based tool that appears in your browser when your application raises an unhandled exception.

### Flask Responses

When Flask invokes a view function, it expects its return value to be the response to the request. In most cases the response is a simple string that is sent back to the client as an HTML page.
+ A very important part of the HTTP response is the status code, which Flask by default sets to 200, the code that indicates that the request was carried out successfully.

```Python
@app.route('/') 
def index(): 
    return '<h1>Bad Request</h1>', 400
```

### A redirect response type

```Python
from flask import redirect
@app.route('/') def index(): return redirect('http://www.example.com')
```

### The abort() function: is used for error handling —> returns status code 404

```Python
from flask import abort
@app.route('/user/<id>') 
def get_user(id): 
    user = load_user(id) 
    if not user: 
        abort(404)
    return '<h1>Hello, {}</h1>'.format(user.name)
```