## While Loops

------

### Tip

> To modify a list as you work through it, use a while loop --> you shouldn’t modify a list inside a for loop because Python will have trouble keeping track of the items in the list. 

```python
current_number = 1
while current_number <= 5:
	print(current_number)
	current_number += 1
```

### Letting the User Choose When to Quit

```python
prompt = "\nTell me something, and I will repeat it back to you:"
prompt += "\nEnter 'quit' to end the program. "
message = ""
while message != 'quit':
	message = input(prompt)
	print(message)
```

### Using a Flag

> when many different events could cause the program to stop running ~> 

```python
prompt = "\nTell me something, and I will repeat it back to you:"
prompt += "\nEnter 'quit' to end the program. "
message = ""

active = True
while active:
	message = input(prompt)
	if message == 'quit':
		active = False
	else: print(message)
```

### **Using break** to Exit a Loop 

```python
prompt = "\nTell me something, and I will repeat it back to you:"
prompt += "\nEnter 'quit' to end the program. "
message = ""

while True:
	city = input(prompt)
	if city == 'quit':
		break
	else:
		print(city.title())
```

### Using continue in a Loop 

> Return to the beginning of the loop 

~> prints only the odd numbers 

```python
current_number = 0
while current_number < 10:
	current_number += 1
	if current_number % 2 == 0:
		continue
	print(current_number)
```

### Moving Items from One List to Another

```python
unconfirmed_users = ['alice', 'brian', 'candace']
confirmed_users = []

while unconfirmed_users:
	current_user = unconfirmed_users.pop()
	print("Verifying user: " + current_user.title())
	confirmed_users.append(current_user)
```

### Removing All Instances of Specific Values from a List

```python
pets = ['dog', 'cat', 'dog', 'goldfish', 'cat', 'rabbit', 'cat']

while 'cat' in pets:
	pets.remove('cat')
	print(pets)
```

