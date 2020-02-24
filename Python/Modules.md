## Modules

------

Python code that is kept in a separate file.

### Importing an Entire Module

**→ pizza.py**

```python
def make_pizza(size, *toppings): 
     """bla bla."""  
```

**→ making_ pizzas.py** 

```python
import pizza
pizza.make_pizza(16, 'pepperoni') 
```

### Importing Specific Functions

**→ making_ pizzas.py**

```python
from pizza import make_pizza
make_pizza(16, 'pepperoni') 
```

###  Importing All Functions in a Module

--> you can call each function by name without using the dot notation 

```python
from pizza import *  
make_pizza(16, 'pepperoni') 
```

### Using as **to Give a** **Function an Alias** 

--> Can be used when you have a function with the same name as the function that you are importing 

```python
from pizza import make_pizza as mp
mp(16, 'pepperoni') 
```

### Using as to Give a Module an Alias

```python
import pizza as p  
p.make_pizza(16, 'pepperoni') 
```

