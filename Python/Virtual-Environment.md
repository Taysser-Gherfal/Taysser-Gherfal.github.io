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

