# 1a 

```python
weight_kg = float(input("? kg\n"))
weight_lb = weight_kg * 2.2
print(f"{weight_lb} pounds")
```

# 1b

```python
netBalance = float(input("? balance\n"))
payment = float(input("? payment\n"))
d1 = int(input("? days in billing cycle\n "))
d2 = int(input("? number of days payment made before billing cycle\n"))
interest_rate = float(input("? monthly interest rate/n"))
averageDailyBalance = (netBalance * d1 - payment * d2) / d1
interest = averageDailyBalance * interest_rate
print(f"The interest on balance is: {interest}")
```

# 1c 
```python
import math
x = float(input("Enter average speed of car A (mph): "))
y = float(input("Enter average speed of car B (mph): "))
hours = float(input("Enter elapsed hours: "))
minutes = float(input("Enter elapsed minutes: "))
t = hours + minutes / 60
distance_A = x * t
distance_B = y * t
distance = math.sqrt(distance_A ** 2 + distance_B ** 2)
print(f"Distance between two cars is {distance} mile(s)")
```

# 2a 
a. hello = "hello"  Valid just changing it so you wouldn't have to put "" around hello every time you wanted "hello"

b. _var = 100 Valid underscores in front don't change anyth other than the name

c. !var_1 = 200   SyntaxError, cannot start with exclamation

d. print = "print me"  Runs, but it would fail if you wanted to print something

e. False = 0 SyntaxError, cannot assign things to False, True, or None
