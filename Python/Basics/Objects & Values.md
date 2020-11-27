## Objects & Values

```python
a = [1, 2, 3]
b = [1, 2, 3]
c = b
```
The two lists are equivalent because they have the same elements, but not identical because they are not the same object.
- a is b --> False
- b is c --> True

When passing a list to a function, the function gets a reference to the list. If the function modifies the list, the caller sees the change. This happens to mutable objects like lists, but doesn't happend to immutable objects like strings.
> **Mutable objects:** objects you can change their existing elements like lists. Immutable objects on the other hand, can't be changed
> ```python
> numbers = [17, 123]
> numbers[1] = 5
> ```

### Remember:
- Most lists methods modify the argument and returns None. This is the opposite of string methods
    ```python
    word = word.strip()
    l = list(s)
    ```
- You can make a copy of your list and keep the original
    ```python
    orig = t[:]
    ```