## Object-Oriented

------

Imagine if you could create individual copies of functions with their own sets of variables and data whenever you need them!

Classes need objects to be created which hold the data. Classes are just templates that don't do anything on their own. This is different to functions that can be called straight away from our main code.

- Functions inside of classes are known as methods
- An object is an instance of a class - a working version of it

```python
class Employee:
    # This is a class variable shared between all instances of a class to keep track of how many employees created
    employee_count = 0
    
    # This method is run automatically when objects are created where parameters are passed from the main code
    def _init_(self, passed_name, passed_number):
        # variables owned by specific instance of a class
        self.name = passed_name
        self.number = passed_number
        Employee.employee_count += 1
        
    def show(self):
        print("Name:", self.name)
        print("Number", self.number)
        
first = Employee("Bob", 1234).show()
second = Employee("Steve", 4321).show()

print("Number of employees", Employee.employee_count)
```

### Getters, setters and logic

Sometimes it is valuable for classes to perform some checks on values before assigning them to attributes - so that a class can make sure that only valid data is getting sent to it. 

```python
class Myclass:
    def _init_(self, num_passed):
        self.num = num_passed
    
    # method called when the program gets the value of 'num'
    @property
    def num(self):
        print("Getting a number")
        return self._num
    
    # method called when the program sets the value of 'num'
    @num.setter
    def num(self, num_passed):
        print("Setting number")
        if num_passed > 1000:
            print("Rounding to 1000")
            self._num = 1000
        else:
            self._num = num_passed
            
x = Myclass(123)
print(x.num)

x.num = 9000
print(x.num)
```

