# 1a

```python
my_tuple = tuple(input("Enter value: ") for _ in range(5))
print(my_tuple)
```

# 1b

tuples are immutable. only way is to create a new tuple
```python
my_tuple = (1, 2, 3)
temp = list(my_tuple)
temp[0] = 100
my_tuple = tuple(temp)
```

# 1c

```python
my_tuple = (1,2,3,4,3,2,1,2,3,5,4,3,2,1)

counts = {}
for item in my_tuple:
    counts[item] = counts.get(item, 0) + 1

for value, count in counts.items():
    if count > 1:
        print(value, "repeated", count, "times")
```

# 1d

```python
my_tuple = (1,2,3,4,3,2,1,2,3,5,4,3,2,1)
print("Before:", id(my_tuple))

my_tuple = my_tuple + my_tuple
print("After:", id(my_tuple))

print("Same object?", id(my_tuple) == id(my_tuple))
```
The `+` operation creates a **brand new tuple** object (concatenation doesn't modify in place, since tuples are immutable) — so `id(my_tuple)` changes after the reassignment, proving it's a different object in memory.

# 1e

```python
x = (1,2,3,4)
x.append(1)     # Illegal: tuples are immutable, no append() method exists for them
x[1] = "hello"  # Illegal: can't assign to an index because tuples don't support item assignment
del x[2]        # Illegal: can't delete an individual element from an immutable tuple
```

# 2a

```python
(one, two, three, four) = (1, 2, 3, 4)
print(type(one), type(two), type(three), type(four))
```
Each variable is an `int` — unpacking just assigns each individual value from the tuple to a variable, keeping that value's own type.

# 2b

```python
x = (1, 2, 3, 4)
a, b, *c = x
print(a, b, c)  # 1 2 [3, 4]
```

# 2c

```python
x = (1, 2, 3, 4)
a, *b, c = x
print(a, b, c)
```
Output: `1 [2, 3] 4` — `a` takes the first value, `c` takes the last value, and `*b` absorbs everything in between as a list.

# 3

```python
my_x = [100, 200, 300, 400]
my_y = (200, 300, 400, 500)

for i in range(len(my_x)):
    print("my_x index", i, "->", id(my_x[i]))

for i in range(len(my_y)):
    print("my_y index", i, "->", id(my_y[i]))
```

| Index | my_x | my_y |
|-------|------|------|
| 0 | id(100) | id(200) |
| 1 | id(200) | id(300) |
| 2 | id(300) | id(400) |
| 3 | id(400) | id(500) |

Since all these values (100–500) fall within CPython's small-int cache (-5 to 256... note 400 and 500 fall outside that range and may get fresh addresses), values that are cached (100, 200, 300, 400) will reuse the same memory address wherever they appear — so `my_x[1]` (200) and `my_y[0]` (200) point to the same address. Values outside the cached range (like 500) get a freshly allocated address each time they're created, so `my_y[3]` (500) won't share memory with anything unless another variable also happens to reference that exact same object.
