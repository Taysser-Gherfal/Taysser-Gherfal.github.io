## Built in Modules

------

### 'SYS' Module

> Provides two usefull things:
>
> - The CMD parameters (aka 'arguments')
> - Terminating a program with an error or success code 'exit'
>
> ```python
> from sys import argv, exit
> 
> if len(argv) == 1:
>     print("No filename specified!")
>     exit(1)
> ```
>
> ```python
> import sys
> 
> if len(sys.argv) == 1:
>     print("No file name specified")
>     sys.exit(1)
>     
> try:
>     file_data = open(sys.argv[1], "r").read()
>     print(file_data)
>     
> except OSError as err:
>     print("File couldn't be opened")
>     print(err)
> ```
>
> - Which OS is being used to run the code 'sys.platform'
>   - 'win32' - for windows even if it's 64-bit
>   - 'linux' - for linux
>   - 'darwin' - for macOS
> - Which Python is being used 'sys.version_info'
>   - a tuble containing the major, minor and micro version numbers
>
> ```python
> import sys
> 
> print("Running on:", sys.platform)
> print("Python version:", end="")
> print(sys.version_info[0], sys.version_info[1], sep=".")
> 
> if sys.version_info[3] != "final":
>     print("Error: please use a released version of Python")
>     sys.exit(1)
> ```
>
> 

### 'OS' Module

> Let's your Python programs interface with the operation system
>
> - Execute commands like the regular command line
>
> ```python
> import sys, os
> print("Clearning screen...")
> 
> if sys.platform == "win32":
>     os.system("cls")
> else:
>     os.system("clear")
> 
> print("Done!")
> ```
>
> - Getting the size of the terminal window
>
> ```python
> import os
> 
> width, height = os.get_terminal_size()
> 
> print("Window width:", width)
> print("Window height:", height)
> ```

### 'Time' module

> - Make you program pause for a number of seconds - you can use floating point numbers for less than a second!
>
>   ```python
>   import time
>   print("Counting to 10 seconds...")
>   for x in range(1,11):
>       time.sleep(1)
>       print(x)
>   ```
>
> - Get the current time and date
>
>   ```python
>   import time
>   mytime = time.strftime("%H:%M")
>   print(mytime)
>   ```
>
>   ```python
>   import time
>   # to get the raw hour nubmer
>   hour = int(time.strftime("%H"))
>   ```