## Functions

------

Modularity in programming is essential when you start working on large projects → **Functions** help you to achieve this by dividing tasks into individual, self-contained code chunks that:
    • You can work on them individually
    • Re-use them in other programs

> Every function should have **one specific job**

> Similar to variables functions names:
>
> - Can't start with a number
> - Can't include punctuation
> - Can't be the same name of an existing function
> - It is good to have a descriptive function name → **get_users_name**

> ### Infinite Recursion
>
> If you call a function inside itself, Python will not be happy and will give you “Maximum recursion depth exceeded error” to stay away from running out of memory!

> ### Local Variables
>
> - When Python finishes executing a function, all of the local variables are freed in memory
> - They are only available inside of functions

> ### Global Var
>
> Only use global variables where absolutely necessary → Keep things modular!
>
> ```python
> def update():
>     global x
>     x = 9000
> ```

------

### Passing Information to a Function

```python
def greet_user(username):
	print("Hello, " + username.title() + "!")

greet_user('jesse')
```

### Passing Multiple Pieces of Data to Functions

> **Positional Arguments** --> Order Matters
>
> ```python
> def describe_pet(animal_type, pet_name):
> 	print("My " + animal_type + "'s name is " + pet_name.title() + ".")
> 
> describe_pet('hamster', 'harry')
> ```

> **Default Values** --> if you notice that most of the calls to describe_pet() are being used to describe dogs
>
> ```python
> def describe_pet(pet_name, animal_type='dog'): 
> 
> describe_pet(pet_name='willie')
> ```

> **Keyword Arguments** --> a name-value pair that you pass to a function
>
> ```python
> def describe_pet(animal_type, pet_name):
> 	print("My " + animal_type + "'s name is " + pet_name.title() + ".")
> 
> describe_pet(animal_type='hamster', pet_name='harry')
> ```

> **Passing an arbitrary number of arguments** -----> Python makes a **tuple** def make_pizza(***toppings**): 
>
> ```python
> def make_pizza(*toppings):
> 	print("\nMaking a pizza with the following toppings:")
> 	for topping in toppings:
> 		print("- " + topping)
> 
> make_pizza('pepperoni')
> make_pizza('mushrooms', 'green peppers', 'extra cheese')
> ```

> **Mixing Positional and Arbitrary Arguments** 
>
> ```python
> def make_pizza(size, *toppings):  
> 
> make_pizza(12, 'mushrooms', 'green peppers', 'extra cheese') 
> ```
>
> ```python
> def build_profile(first, last, **user_info):
> 	"""Build a dictionary containing everything we know about a user."""
> 	profile = {}
> 	profile['first_name'] = first
> 	profile['last_name'] = last
> 	for key, value in user_info.items():
> 		profile[key] = value
> 	return profile
> 
> user_profile = build_profile('albert', 'einstein', location='princeton', field='physics')
> print(user_profile)
> ```
>
>  ***\*user_info** cause Python to create an empty **dictionary**!

------

### Return Values

```python
def get_formatted_name(first_name, last_name):
	full_name = first_name + ' ' + last_name
	return full_name.title()

musician = get_formatted_name('jimi', 'hendrix')
print(musician)
```

> **Return Multiple Pieces of Data**
>
> ```python
> def my_function():
>     return 50, 90
>     
> x,y = my_function()
> ```
>
> **Return a tuble, list, or a dictionary** 
>
> ```python
> def my_function():
>     return(50, 90)
>     
> mytuble = my_function()
> print(mytuble[1])
> ```

