## Numbers

------

### Note:

Two multiplication symbols ***\*** represent **exponents**

### Numerical Lists:

- **Range**
  for value in **range**(1,5):

  ```python
  for i in range(0,5):
  	print(i)
  ```

- **Convert to a list**  

  numbers = list(**range**(1,6)) 
  **even**_numbers = list(range(2,11,**2**)) → بعد كل قداش

  ```python
  numbers = list(range(0,5))
  print(numbers)
  '''[0, 1, 2, 3, 4]'''
  
  even_numbers = list(range(2,11,2))
  print(even_numbers)
  '''[2, 4, 6, 8, 10]'''
  ```

- **List of Squares**

  squares.append(value***\***2)

  ```python
  squares = []
  for value in range(0,10):
  	squares.append(value**2)
  
  print(squares)
  ```

  List Comprehensions: **faster way😌** 

  squares = **list**(**value\**2** for value in range(1,10))

  ```python
  squares = list(value**2 for value in range(1,10))
  print(squares)
  ```

- **Simple Statistics:** **min**(), **max**(), **sum**() 

  ```python
  squares = list(value**2 for value in range(1,11))
  print(squares)
  print("Max: "+ str(max(squares)))
  print("Min: "+ str(min(squares)))
  ```

  