# 1a

```python
my_dict = {
    "apple": 1.50,
    "banana": 0.75,
    "carrot": 0.60,
    "date": 3.00,
    "egg": 0.25,
    "fish": 8.00,
    "grape": 2.50,
    "honey": 6.00,
    "ice": 1.00,
    "jam": 4.50
}
print(my_dict)
print(len(my_dict))
```

# 1b

```python
my_user_dict = {}
count = 1

while True:
    ssn = input("Enter SSN: ")
    name = input("Enter Name: ")

    my_user_dict["SSN_" + str(count)] = ssn
    my_user_dict["Name_" + str(count)] = name

    again = input("Do you want to continue (Y/N)? ")
    if again == "N" or again == "n":
        break
    count += 1

print(my_user_dict)
```
Two keys are needed per person (SSN and Name), so each entry uses a unique numbered key (`SSN_1`, `Name_1`, `SSN_2`, `Name_2`, ...) since a plain dictionary can't hold duplicate keys.

# 1c

```python
data = [('Name', 'Sarah Connor'),
        ('Date of birth', '1 Jan 1980'),
        ('Address', '1000 Black Mountain Drive'),
        ('Name', 'Jim Hawkins')]

result_dict = {}

for pair in data:
    if len(pair) != 2:
        print("Invalid pair:", pair, "- must have exactly a key and a value")
        continue

    key, value = pair

    if key in result_dict:
        new_key = input("Key '" + key + "' already exists. Please enter a new key: ")
        result_dict[new_key] = value
    else:
        result_dict[key] = value

print(result_dict)
```

# 1d

```python
data = [('Name', 'Sarah Connor'),
        ('Date of birth', '1 Jan 1980'),
        ('Address', '1000 Black Mountain Drive')]

my_dict = {}
for key, value in data:
    my_dict[key] = value

print(my_dict)
```

# 1e

```python
text = "The tiger (Panthera tigris) is a large cat and a member of the genus Panthera native to Asia. It has a powerful, muscular body with a large head and paws, a long tail and orange fur with black, mostly vertical stripes. It is traditionally classified into nine recent subspecies, though some recognise only two subspecies, mainland Asian tigers and the island tigers of the Sunda Islands."

cleaned = ""
for char in text:
    if char.isalpha() or char == " ":
        cleaned = cleaned + char

words = cleaned.split()

word_count = {}
for word in words:
    if word in word_count:
        word_count[word] = word_count[word] + 1
    else:
        word_count[word] = 1

print(word_count)
```

# 2a

```python
d_orig = {123: "Coconut"}
d_copy = d_orig.copy()

d_copy[123] = "Mango"

print(d_orig)  # {123: 'Coconut'} - unaffected
print(d_copy)  # {123: 'Mango'}
```

# 2b

Using `.copy()` (a shallow copy) creates a separate dictionary object, so changes to `d_copy` don't affect `d_orig`. Without `.copy()`, `d_copy = d_orig` just makes both names point to the *same* dictionary object in memory, so changing one changes both.

# 2c

```python
d = {}
d[[1, 2, 3]] = "value"
```
This raises `TypeError: unhashable type: 'list'` because dictionary keys must be hashable (immutable), and lists are mutable — Python can't guarantee a list's hash value stays constant if its contents change, so it's disallowed as a key. Using a tuple instead (`d[(1,2,3)] = "value"`) would work since tuples are immutable.
