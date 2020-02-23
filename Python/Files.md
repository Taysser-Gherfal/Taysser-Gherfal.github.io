## Python > Files

------

You should use exception handling when saving files → in case the location is not allowed by the OS

```Python
try:
    # your saving code
except OSError as err:
    print(err)
```

### Text Files

| Modes |            |
| ----- | ---------- |
| w     | over write |
| r     | read       |
| a     | append     |

To do any work with a file, even just printing its contents, 

1. you first need to **open** the file to access it. 
2. **Read** the entire contents of the file and store it as ***one long string in contents*** 
3. You can trust that **Python will close the file automatically** when the time is right. 

```python
myfile = open("hello.txt", "w") #opens file object
myfile.write("Hello")
myfile.close()
```

More Pythonic

```python
with open('pi_digits.txt') as file_object: 
    contents = file_object.read() 
    print(contents) 
```

```python
with open("hello.txt","w") as myfile:
    myfile.write("Hello")
```

------

### <u>Structured Data</u> → Comma Separated Value - CSV

> Adding the content of a list to a dictionary 
>       ⇒ Mike, 1234
>       ⇒ Bob, 242
>
> ```python
> employees = {}
> 
> try:
>     myfile = open("data.txt", r)
>     for text_line in myfile:
>         mylist = text_line.split(",")
>         employees[mylist[0]] = int (mylist[1].rstrip())
>     myfile.close()
>     
> except OSError as err:
>     print("File couldn't be opened")
>     print(err)
> ```
>
> **Note:** It is good practice to clean the data before using it → mylist[1].rstrip())

### <u>Searching Files Line By Line</u>

> ```python
> text_list = open("data.txt", "r").readlines()
> 
> for counter, line in enumerate(text_list):
>  loc = line.lower().find("spring")
>  
>  if loc != -1:
>      print("Found on line", counter + 1, "position", loc)
> ```
>
> <u>Python String</u> **str.find(sub[, start[, end]])**
>
> This function returns the lowest index in the string where substring “sub” is found within the [slice](https://www.journaldev.com/23584/python-slice-string) s[start:end].
>
> - **start** default value is 0 and it’s an optional argument.
>
> - **end** default value is length of the string, it’s an optional argument.
>
> - If the substring is not found then **-1** is returned.

### <u>Reading Binary Files</u>

> ```python
> # read file in binary mode
> mydata = open("image.dat", "rb").read()
> 
> # go over every byte
> for x in mydata:
>     print(x, end="")
> ```
>
> **For Large Files** → it is better to not read the hall file once, but load individual bytes to save memory
>
> ```python
> with open("image.dat", "rb") as myfile:
>     #read one byte    
>     byte = myfile.read(1) #byte object
>     while byte != b"":
>         print(ord(byte), end = "")
>         byte = myfile.read(1)
> ```

### <u>Pickling</u>

> Is the process of converting Python data objects / lists or dictionaries / into a compact binary form that can be stored in a file and read back quickly.
>
> - **Cons** - You can't edit pickled Python data with text editor
> - **Pros** - Very simple to use + does not require any complicated parsing
>
> | Modes |                     |
> | ----- | ------------------- |
> | wb    | binary mode - write |
> | rb    | binary mode - read  |
>
> .p → for consistency - to know that it is a pickle file
>
> **Writing**
>
> ```python
> import pickle
> 
> employees = {"Bob":123, "Steve":567}
> 
> with open("employees.p", "wb") as myfile:
>     pickle.dump(employees, myfile)
> ```
>
> **Reading**
>
> ```python
> import pickle
> 
> with open("employees.p", "rb") as myfile:
>     employees = pickle.load(myfile)
>     
> print(employees)
> ```

### <u>JSON:</u> JavaScript Object Notation

> A plain text format for storing data
>
> ```python
> import json
> 
> employees = {"Bob": 123, "Steve": 455}
> with open("employees.json", "w") as myfile:
>  json.dump(employees.myfiles)
> ```
>
> Reading the price of the first item
>
> ```python
> import json
> 
> with open("data.json", "r") as myfile:
>  mydata = json.load(myfile)
>  
> print(mydata[0]["price"])
> ```
>
> To print the content of json on the screen:
>
> ```python
> print(json.dumps(employees, indent=4s))
> ```
>
> → indentations makes it easier to read data
>
> **Complete Example:**
>
> - Load the username, if it has been stored previously. 
> - Otherwise, prompt for the username and store it. 
>
> ```python
> import json 
>  
> def get_stored_username(): 
>     """Get stored username if available.""" 
>     filename = 'username.json' 
>     try: 
>         with open(filename) as f_obj: 
>             username = json.load(f_obj) 
>             except FileNotFoundError: 
>                 return None 
> 	else: 
>         return username 
>  
> def get_new_username(): 
>     """Prompt for a new username.""" 
>     username = input("What is your name? ") 
>     filename = 'username.json' 
>     with open(filename, 'w') as f_obj: 
>         json.dump(username, f_obj) 
> 	return username 
>  
> def greet_user(): 
>     """Greet the user by name.""" 
>     username = get_stored_username() 
>     if username: 
>         print("Welcome back, " + username + "!") 
> 	else: 
> 		username = get_new_username() 
> 		print("We'll remember you when you come back, " + username + "!") 
>  
> greet_user() 
> ```
>
> 

