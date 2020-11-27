## Python > Built In Functions

------

### list() & split()

> - **list()** converts a string to a list by breaking it into individual letters 
> - **split()** breaks a string into words
> ```python 
> s = 'a number of strings'
> l = list(s)
> w = split(s)
>```

### exec()

> Runs a program within a program → runs the code as a part of the current program - if x is defined within the program, you can print it for example
>
> ```python
> code = input ("Enter code:")
> exec(code)
> ```

### chr()

> Display characters that are not on the keyboard using Unicode → On Windows you need to change the character set for this to work
>
> ```python
> print(chr(8364))
> ```

### print extra parameter

> Stop print from jumping to a new line
>
> ```python
> print(x, end"")
> ```

### len

> Gets the length of a string 
>
> ```python
> len(name)
> ```

### pow

> Returns the first number raised to the power of the second → first^second 
>
> ```python
> pow(first,second)
> ```

### round

> Rounds down floating point numbers to x decimal points
>
> ```python
> round(number,x)
> ```