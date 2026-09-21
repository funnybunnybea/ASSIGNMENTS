# 1a

```python
def convert(*values, direction):
    results = []
    for value in values:
        try:
            value = float(value)
        except ValueError:
            print("Invalid input:", value, "- must be a number")
            continue

        if direction == "kpl_to_mpg":
            converted = value * 2.35215
            results.append(converted)
        elif direction == "mpg_to_kpl":
            converted = value / 2.35215
            results.append(converted)
        else:
            print("Invalid direction")

    return results

choice = input("Convert from kpl to mpg, or mpg to kpl? (kpl/mpg): ")
values = input("Enter value(s) separated by spaces: ").split()

if choice == "kpl":
    print(convert(*values, direction="kpl_to_mpg"))
elif choice == "mpg":
    print(convert(*values, direction="mpg_to_kpl"))
else:
    print("Invalid choice")
```
Conversion factor: 1 km/L ≈ 2.35215 mpg (since 1 mile ≈ 1.60934 km and 1 gallon ≈ 3.78541 L).

# 1b

```python
def print_reversed(*args):
    for item in reversed(args):
        print(item)

print_reversed(1, 2, 3, 4)
```
`*args` collects any number of unnamed arguments into a tuple, and `reversed()` iterates through it backwards.

# 1c

```python
def modify_list(lst):
    lst.append(100)       # visible outside - mutates the original object

def reassign_list(lst):
    lst = [1, 2, 3]        # NOT visible outside - just rebinds the local name

my_list = [1, 2, 3]
modify_list(my_list)
print(my_list)  # [1, 2, 3, 100] - changed

reassign_list(my_list)
print(my_list)  # [1, 2, 3, 100] - unchanged, reassignment doesn't affect caller
```
Lists and dictionaries are mutable, so operations that change their *contents in place* (`.append()`, `.pop()`, `[key] = value`, `.update()`) are visible outside the function, since the function receives a reference to the same object. Reassigning the parameter itself (`lst = ...`) only changes the local variable, not the object the caller holds.

To minimize risk of unwanted side effects, pass a copy instead of the original:
```python
def safe_modify(lst):
    lst = lst.copy()
    lst.append(100)
```

# 1d

```python
x = 5

def funct_1():
    x = 3   # creates a new local variable, doesn't touch global x

def funct_2():
    global x
    x = 2   # modifies the global x directly
```
After `funct_1()`: `x` is still **5** (local assignment doesn't affect the global).
After `funct_2()`: `x` becomes **2** (the `global` keyword lets it modify the outer variable).

# 2. Troubleshooting

**Part 1:**
```python
def my_func(a, b, *c):
    print(c)

my_func(1, 2, 3, 4, 5, 6)
```
The original code used `**c` (double star), which is for keyword arguments (`key=value` pairs) and expects a dictionary. Since the call passes plain positional arguments, it should use `*c` (single star) to collect them into a tuple.

**Part 2:**
```python
def my_func_global():
    x = 100
    print(x)  # if you want to see 100, print inside the function

x = 10
my_func_global()
print(x)  # prints 10
```
It prints `10` because `x = 100` inside `my_func_global()` creates a **local** variable `x`, since there's no `global x` declaration in that function. This local `x` only exists inside the function and disappears after it returns — it never touches the outer, global `x`, which stays at 10. To make the function modify the global variable, you'd need to add `global x` inside `my_func_global()`.
