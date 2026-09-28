# Part 1
1 Bad input. Code is fine, user typed the wrong data
2 Bug. Typo in the code
3 Bad input. Code works, user entered zero

# Part 2
Operation: int on empty input
Why: int cannot convert an empty string
Exception name: ValueError says the value was the wrong kind
Input 0: no ValueError, int 0 works, but 1 / value raises ZeroDivisionError

# Part 3
```python
try:
    value = int(input("Enter an integer: "))
    print("You entered:", value)
except ValueError:
    print("Not a valid integer")
```
4 prints You entered 4
abc prints Not a valid integer
empty prints Not a valid integer

# Part 4
2: runs A B C D, skips nothing, no exception
0: runs A B D, skips C, ZeroDivisionError
hello: runs A D, skips B C, ValueError, B fails bec int("hello") breaks to the except skipping C toox

# Part 5
```python
try:
    value = int(input("Enter an integer: "))
    print("Reciprocal:", 1 / value)
except ValueError:
    print("Enter a valid integer")
except ZeroDivisionError:
    print("Cannot divide by zero")
```
Only one except runs because an exception has one type and Python runs the first match

# Part 6
A ValueError, hello is not a number
B ZeroDivisionError, modulo by zero
C TypeError, list index must be an integer
D AttributeError, lists have no depend method

# Part 7
Purpose: catches any exception not matched above like a type error or attribute error
Runs when no earlier except statement matches
Must be last or it would catch everything first
Specific handlers say exactly what went wrong

# Part 8
SyntaxError
Missing colon after if value > 0
Python cannot run the code at all so it must be fixed, not caught

# Part 9
| Input | Path | Expected |
|---|---|---|
| 5 | if | Positive |
| -5 | elif | Negative |
| 0 | else | Zero |

One passing test only checks one path, the others could still be broken

# Part 10
Works for 0: yes, it only uses the else branch
Bug is in the elif branch, prin instead of print
Any negative number exposes it
Testing one path can hide bugs in other paths
```python
value = float(input("Enter a number: "))

if value > 0:
    print("Positive")
elif value < 0:
    print("Negative")
else:
    print("Zero")
```

# Part 11
Expected: 12.50 * 4 = 50.0
Actual: 16.5
```python
def calculate_total(price, quantity):
    print("price:", price, "quantity:", quantity)
    total = price * quantity
    print("total:", total)
    return total

price = float(input("Price: "))
quantity = int(input("Quantity: "))

result = calculate_total(price, quantity)
print("Total:", result)
```
First print shows the inputs are correct
Second print shows the total, which exposed that + was used instead of *
Fix: change + to *
After fix the result is 50.0 and the debug prints can be removed

# Part 12
```python
try:
    num1 = int(input("Enter first integer: "))
    num2 = int(input("Enter second integer: "))
    print("Quotient:", num1 / num2)
except ValueError:
    print("Enter valid integers")
except ZeroDivisionError:
    print("Cannot divide by zero")

print("Done")
```
| Input 1 | Input 2 | Path | Expected |
|---|---|---|---|
| 10 | 2 | try succeeds | 5.0 |
| 10
