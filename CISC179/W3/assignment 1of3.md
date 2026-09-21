### 5a.
```python
n1 = int(input("Enter first number: "))
n2 = int(input("Enter second number: "))
n3 = int(input("Enter third number: "))

if n1 >= n2 and n1 >= n3:
    largest = n1
elif n2 >= n1 and n2 >= n3:
    largest = n2
else:
    largest = n3

print("The largest number is:", largest)
```

### 5b. 
```python
num = int(input("Enter an integer: "))

# Approach 1: Modulus
if num % 2 == 0:
    print("Even")
else:
    print("Odd")


# Approach 2: Bitwise AND
if num & 1 == 0:
    print("Even")
else:
    print("Odd")


# Approach 3: Division

if (num / 2) == (num // 2):
    print("Even")
else:
    print("Odd")
```

### 5c. 
```python
percent = int(input("Enter percentage: "))

if percent > 90:
    print("Grade: A - Work of genuinely superior quality.")
elif percent >= 80:
    print("Grade: B - Passing performance in the upper distribution of passing grades.")
elif percent >= 71:
    print("Grade: C - Passing performance in the center of the distribution of passing grades.")
elif percent >= 65:
    print("Grade: D - Passing performance in the lower distribution of passing grades.")
elif percent >=0:
    print("Grade: F - Failing performance, does not meet basic requirements.")
else:
    print("N/A")
```

### 5d. Truth Table (and, or, not)
```python
op = input("Enter operator (and/or/not): ")

for a in (True, False):
    for b in (True, False):
        if op == "and":
            print(a, b, "->", a and b)
        elif op == "or":
            print(a, b, "->", a or b)
        elif op == "not":
            print(a, "->", not a)
```

### 5e. Even/Odd Using Bitwise AND 
```python
num = int(input("Enter an integer: "))

if num & 1 == 0:
    print(num, "is Even")
else:
    print(num, "is Odd")
```

### 6.  Greeting
```python
name = input("What's your name? ")
time = int(input("What time is it? "))


if time < 1200:
    print("Hi " + name + ", good morning!")
elif time < 1800:
    print("Hi " + name + ", good afternoon!")
else:
    print("Hi " + name + ", good evening!")

print("Good Bye")
```

### 7. Output 
one
two
