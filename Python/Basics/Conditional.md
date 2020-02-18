## Conditional Test

------

### Checking for Equality

> car **==** 'audi' 
> car **!=** 'audi' 
> age **<=** 21 

### Checking Multiple Conditions

> (age_0 >= 21) **and** (age_1 >= 21) 
> (age_0 >= 21) **or** (age_1 >= 21) 

### Checking Whether a Value Is in a List

> if 'mushrooms' **in** requested_toppings: 
> if user **not in** banned_users: 

### <u>Tips:</u>

> - if you want **only one block of code to run**, use an **if-elif-else chain**.
> - If **more than one block** of code needs to run, use **a series of independent if statements**.
> - **if number % 2 == 0** the number is even. Otherwise, it’s odd. 
>
> ```python
> a=1
> while a <=10:
>    if a%2 ==0:
>        print(a)  
>    a+=1
> ```



**Elif** --> Python **does not require an else** block at the end of an if-elif chain. 

```python
age = 12
if age < 4:
	price = 0
elif age < 18:
	price = 5
else:
	price = 10
print("Your admission cost is $" + str(price) + ".")
```

