## Dictionary {'': , '':, }

------

- With tubles & lists you can't refer to items using names
- Key names have to be unique

```python
alien = {'color': 'green', 'points': 5}
print(alien['color'])

''' green '''
```

### Adding / Updating Key-Value Pair

>
> alien ['type'] = 'P'

```python
alien = {'color': 'green', 'points': 5}

alien ['type'] = 'P'
print(alien)

''' {'color': 'green', 'points': 5, 'type': 'P'} '''
```

### Removing Key-Value Pairs

```python
del alien ['type']
```

### Finding if a dictionary has a specific element

> *Does dictionary contain **key** name text?*

```python
if text in employees:
    print(employees[text])
```

### Looping Through All Key-Value Pairs

> for key, value in alien**.items()**:  

```python
alien = {'color': 'green', 'points': 5}

for k,v in alien.items():
	print('key: ' + k)
	print('value: ' + str(v))
```

### Looping Through All the Keys

> for i in alien**.keys()**:       
> for i in alien 

```python
alien = {'color': 'green', 'points': 5}
	
for i in alien:
	print(i)

for i in alien.keys():
	print(i)
```

### Looping Through a Dictionary’s Keys in Order

> for i in **sorted**(alien.keys()):  

```python
alien = {'points': 5, 'color': 'green'}

for i in sorted(alien.keys()):
	print(i)
```

### Looping Through All Values in a Dictionary

> for i in alien**.values()**:  

```python
alien = {'points': 5, 'color': 'green'}

for i in alien.values():
	print(i)
```

### Working with duplicate items

> for i in **set**(alien .values()):

> **Tip:** When you wrap **set()** around a list that contains duplicate items, Python **identifies the unique** items in the list and **builds a set** from those items.

```python
alien = {'points': 5, 'color': 'green', 'color2':'green'}

for i in set(alien.values()):
	print(i)
```

### Nesting

- ##### A List of Dictionaries

```python
# Make an empty list for storing aliens.  
aliens = []

# Make 30 green aliens. 
for alien_number in range(30):
	new_alien = {'color': 'green', 'points': 5, 'speed': 'slow'}
	aliens.append(new_alien)

# Show how many aliens have been created.  
print("Total number of aliens: " + str(len(aliens)))

# Make changes 
for alien in aliens[0:3]:
	if alien['color'] == 'green':
		alien['color'] = 'yellow'
		alien['speed'] = 'medium'
		alien['points'] = 10

# Show the first 5 aliens:
for alien in aliens[:5]:
	print(alien)
	print("...")
```

- ##### A List in a Dictionary

```python
# Store information about a pizza being ordered. 
pizza = {
'crust': 'thick',
'toppings': ['mushrooms', 'extra cheese'],}

# Summarize the order. 
print("You ordered a " + pizza['crust'] + "- crust pizza " + "with the following toppings:")
for topping in pizza['toppings']:
	print("\t" + topping)

# Using the variable name languages to hold each value from the dictionary, because we know that each value will be a list--> 
favorite_languages = {
'jen': ['python', 'ruby'],
'sarah': ['c'],
'edward': ['ruby', 'go'],
'phil': ['python', 'haskell'],}
for name, languages in favorite_languages.items():
	print("\n" + name.title() + "'s favorite languages are:")
	for language in languages:
		print("\t" + language.title())
```

- ##### A Dictionary in a Dictionary

```python
users = {
'aeinstein':{'first': 'albert','last': 'einstein','location': 'princeton',},
'mcurie':{'first': 'marie','last': 'curie','location': 'paris',},
}

for username, user_info in users.items():
	print("\nUsername: " + username)
	full_name = user_info['first'] + " " + user_info['last']
	location = user_info['location']
	print("\tFull name: " + full_name.title())
	print("\tLocation: " + location.title())
```

