# 1a

```python
my_list = list(range(100))
print(type(my_list))


my_list.append(100)      # add item to end
my_list.reverse()        # reverse order in place
print(my_list.count(50)) # count occurrences of 50
print(my_list.index(50)) # find index of 50
```

# 1b

```python
items = [1,2,3,4,5,6,7,8,9,10]

for i in range(3):
    items.insert(0, items.pop(len(items) - 1))

print(items)
```

# 1c

3, three repetitions of [[1,2]] so length is 3

# 1d

```python
my_list_ten = [1, 2, 3, 1, 2, 5, 6, 7, 3, 9]

my_list_ten_mem = [id(item) for item in my_list_ten]
print(my_list_ten_mem)

unique_addresses = set(my_list_ten_mem)
print("Unique addresses:", unique_addresses)
print("Duplicates exist:", len(unique_addresses) != len(my_list_ten_mem))
```

# 1e

```python
del my_list_ten
```

# 1f

```python
my_new_list = [1, 2, 3, 1, 2, 5, 6, 7, 3, 9]
my_new_list_mem = [id(item) for item in my_new_list]

print(my_new_list_mem)
print(my_new_list_mem == my_list_ten_mem)
```
The addresses match for the small-int values because CPython caches integers from -5 to 256 — new variables pointing to the same cached int reuse the same memory address, even though `my_list_ten` no longer exists.

# 1g

```python
import copy

x = [[1, 2, 3], [4, 5, 6], [7, 8, 9]]
y = copy.deepcopy(x)
```
deep copy bc x haas nested lists

# 1h

Yes. A list comprehension can include multiple `for` clauses and multiple `if` conditions

# 1i

```python
sentence = "To be, or not to be, this is the question"
space_count = len([c for c in sentence if c == " "])
print(space_count)
```

# 1j

```python
my_list = [3, 1, 4, 1, 5, 9]

my_list.sort()        # sort list in place
my_list.pop()          # remove and return last item
my_list.extend([2,6])  # add multiple items to end
my_list.insert(0, 100) # insert item at specific index
my_list.remove(1)      # remove first matching value
```
