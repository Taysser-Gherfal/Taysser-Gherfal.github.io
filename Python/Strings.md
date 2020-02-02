## Strings " "

**Strings** are a sequence of spaces in memory all kept under the same variable name

### Title - Lower - Uppercase

```python
name = "ada lovelace"
print(name.title()) # --> Ada Lovelace 
print(name.upper()) # --> ADA LOVELACE 
print(name.lower()) # --> ada lovelace 
```

### Combining or Concatenating

```python
full_name = first_name + " " + last_name
```

### Stripping Whitespace

```python
name = " ada lovelace "
# To ensure that no whitespace exists at the right end of a string 
print(name.rstrip()) 
# To ensure that no whitespace exists at the left side of a string
print(name.lstrip()) 
# strip whitespace from both sides at once 
print(name.strip()) 
# removes all white space
print(name.replace(" ", ""))
```

### Conversion

```python
age = 5
x = str(age)
print(x)
```

