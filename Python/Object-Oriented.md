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

#### Setter 

- Every time the following **'num'** attribute gets a new value, including when it is created during **--init--**, the method under **@num.setter** is called
  - self.__num = 1000 --> a private variable with two under scores to indicate that this is not accessible from outside the class - to prevent an infinite loop

#### Getter

- print(x.num) --> from the main code triggers the **getter**

  @property
      def num(self):

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
            self.__num = 1000
        else:
            self.__num = num_passed
            
x = Myclass(123)
print(x.num)

x.num = 9000
print(x.num)
```



### Inheritance

A way for classes to build upon other classes by inheriting their methods and attributes. That way you can define a base class that has common elements and subclasses which inherit characteristics from the base now.

> Example: A digger for example needs all the a tributes of a vehicle class but also have specific methods for only diggers

```python
class Vehicle:
    def _init_(self,x,y):
        self.x_pos = x
        self.y_pos = y
        self.x_speed = 0
        self.y_speed = 0
        
    def update(self):
        print("Moving")
        self.x_pos += self.x_speed
        self.y_pos += self.y_speed
    
    def render(self):
        print("Drawing")
    
class Digger(Vehicle):
    # initialize the Vehicle bits first
    def _init_(self,x,y):
        Vehicle._init_(self,x,y)
    
    # a specific method for diggers
    def dig(self):
        print("Digging")
   
class plane(Vehicle):
    # initialize the Vehicle bits + special attributes 
    def _init_(self,x,y,z):
        Vehicle._init_(self,x,y,z)
        self.z = z

car = Vehicle(10,20)
car.update()
car.render()

digger = Digger(50,90)
digger.dig

chopper = plane(10,20,30)
chopper.update()
```

