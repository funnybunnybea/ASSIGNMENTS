# 1a

```python
n0 = int(input("Enter a non-negative, non-zero integer: "))
steps = 0

while n0 != 1:
    if n0 % 2 == 0:
        n0 = n0 / 2
    else:
        n0 = 3 * n0 + 1
    steps += 1
    print(n0)

print("steps =", steps)
```

# 1b

```python
i = 0
while i < 5:
    print(i)
```

```python
i = 0
while i < 5:
    print(i)
    i += 1
```

# 1c

```python
while True:
    num1 = int(input("Enter first number: "))
    num2 = int(input("Enter second number: "))
    op = input("Choose operation (+, -, *, /): ")

    if op == "+":
        print("Result:", num1 + num2)
    elif op == "-":
        print("Result:", num1- num2)
    elif op == "*":
        print("Result:", num1 * num2)
    elif op == "/":
        print("Result:", num1 / num2)
    else:
        print("Invalid")

    again = input("Do you want to continue? ")
    if again not in ("Y", "y",):
        print("Have a good day.")
        break
```

# 2a

```python
text = input("Enter text: ")

counts = {}
total = 0

for char in text:
    if char.isalpha():
        char = char.lower()
        total += 1
        if char in counts:
            counts[char] += 1
        else:
            counts[char] = 1

print("Total number of alphabets:", total)
print("Total number of distinct alphabets are:")
for letter, count in counts.items():
    print(letter, "=", count)
```
