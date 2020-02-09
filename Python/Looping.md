## Looping

**For loops** works with **lists of data**

- **Existing list**

```python
mylist=[1,2,3,4]

for a in mylist:
    print(a)
```

- **Not existing list** → use **range** to create a list of numbers on the fly

```python
for a in range(1,11):
    print(a)
    
# shorter than
while a<=10:
    a+=1
```

Using 3 parameters with **range** → the **3rd parameter** is used to define **the size of the increment**

```python
for a in range(1,11,3):
```

- The 3rd parameter can be a **negative number** → **descending order**