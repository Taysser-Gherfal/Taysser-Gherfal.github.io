## Lists [, , ,]

------

**Lists** are Tuples that can be changed!

- **First** item is @ **[0]**
- The **last** item is @ **[-1]**

```python
bicycles = ['trek','cannondale','redline']
# Index Positions Start at 0, Not 1 
print(bicycles[0])
# index -1, Python always returns the last item in the list 
print(bicycles[-1])
```

### Adding Elements to a List

- **.append('ducati')** --> the new element is added **to the end of the list.** 
- **.insert(0, 'ducati')**--> **add a new element at any position** in your list. 

```python
bicycles = ['trek','cannondale','redline']
# adding an item to the end of the list
bicycles.append('ducati')
# adding an item to a position
bicycles.insert(0, 'ducati')
```

### Removing Elements from a List

**del bicycles[0]** --> If you know the position of the item you want to remove

```python
bicycles = ['trek','cannondale','redline']
# If you know the position of the item
del bicycles[1]
print(bicycles)
```

- Want to use the value of an item after you remove it 
  - popped_bicycles  = bicycles **.pop()** --> removes the last item in a list 
  - first = bicycles **.pop(0)** --> to remove an item in a list **at any position**

- **remove()** --> Removing an Item **by Valueless** --> The remove() method deletes only the first occurrence 

```python
bicycles = ['trek','cannondale','redline']
x = bicycles.pop()

print(x) # redline
print(bicycles) # ['trek','cannondale']
y = bicycles.pop(0)
print(y) # trek
bicycles.remove('cannondale')
print(bicycles) #[]

# to remove all instances
for x in range (0, bicycles.count('cannondale')):
    bicycles.remove('cannondale')
```

### Extend the content of one list with the content of another

```python
# All items on myother_list are added onto the end of mylist
mylist.extend(myother_list)
```

### Finding the position of an item in a list

```python
location = mylist.index('cannondale')
```

### Sorting a List

- bicycles **.sort()** --> change the order of the list **alphabetically** + **Numerically**
- bicycles **.sort(reverse=True)** --> **reverse** alphabetical order 
- bicycles **.reverse()** --> it simply **reverses the order of the list** 
- print(**sorted(**bicycles**)**) --> lets you display your list in a particular order but **doesn’t affect the actual order of the list.** 
- Capital letters have more priority in Python → case-insensitive sorting **mylist.sort(key=str.lower, reverse=True)**

```python
bicycles = ['trek','cannondale','redline']

bicycles.sort()
print(bicycles) #['cannondale', 'redline', 'trek']
bicycles.sort(reverse=True)
print(bicycles) #['trek', 'redline', 'cannondale']
print(sorted(bicycles)) #['cannondale', 'redline', 'trek']
print(bicycles) #['trek', 'redline', 'cannondale']
```

### Finding the Length of a List

len(bicycles)

```python
bicycles = ['trek','cannondale','redline']
print(len(bicycles)) #3
```

### Slicing a List

- bicycles [0:2] 
- bicycles [:2] --> Without a starting index, Python **starts at the beginning of the list** 
- bicycles [2:] --> all items **from the third item through the last item** 
- bicycles [-2:] --> output **the last two** items

```python
bicycles = ['trek','cannondale','redline']

print(bicycles [0:2]) # ['trek', 'cannondale']
print(bicycles [:2])  # ['trek', 'cannondale']
print(bicycles [2:])  # ['redline']
print(bicycles [-2:]) # ['cannondale', 'redline']
```

### Copying a List

```python
friend_foods = my_foods[:] 
```

- friend_foods = my_foods --> **doesn't work!** -->  both variables **point** to the same list 

### Making sure the list is not empty

```python
if bicycles:
```

### Finding an item in a list

```python
for requested_topping in requested_toppings:
    if requested_topping in available_toppings:
        print("Adding" + requested_topping + ".")
    else:
        print("Sorry, we don't have" + requested_topping)
```

### Changing the content of a list in a for loop

```python
mylist = [20,60,80]

for counter, x in enumerate(mylist):
    mylist[counter] = x*2
```

