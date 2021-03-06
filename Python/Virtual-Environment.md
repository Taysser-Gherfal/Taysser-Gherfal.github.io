## Virtual Environments

A virtual environment is a copy of the Python interpreter into which you can install packages privately, without affecting the global Python interpreter installed in your system. Virtual environments are very useful because they prevent package clutter and version conflicts in the system’s Python interpreter.

### The standard venv package is not installed by default on Ubuntu

```bash
$ sudo apt-get install python3-venv
```

### Creating a vertual environment

```bash
$ python3 -m venv venv
```

### Activating a vertual environment

Linux / MacOS

```bash
$ source venv/bin/activate
```

Windows

```bash
$ venv\Scripts\activate
```



### Generating a requirements.txt file

```bash
$ pip freeze > requirements.txt
```

### Installing a requirements.txt file

```bash
$ pip install -r requirements.txt
```



### Creating an executable 

```bash
pyinstaller --onefile -w <file.py>
```

