## Arguments

------

```python
import sys

if len(sys.argv) == 1:
    print("No file name specified")
    sys.exit(1)
    
try:
    file_data = open(sys.argv[1], "r").read()
    print(file_data)
    
except OSError as err:
    print("File couldn't be opened")
    print(err)
```

- **argv[0]** → the name of the program 
- **sys.exit(1)** → exit the program with error code 1