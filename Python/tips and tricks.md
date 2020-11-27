## Tips and Tricks
------

### Modulus Operator %

- Check if a number is divisible by another
	```python
	x % y == 0
	```
- Extract the righ-most digits from a number
	```python
	x % 10 #right most
	x % 100 # last 2 digits
	```

### Debugging by bisection
- Instead of checking line by line, break the program in half and check the value
- If the first half is correct, the problem is in the second half

### Methods VS Functions
- Medthods are similar to functions in that they take arguments and return values
- Howver, their syntax is different
	```python
	upper(word) #function
	word.upper() #method
	```