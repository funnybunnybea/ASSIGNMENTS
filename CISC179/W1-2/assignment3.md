 #  1a 

```python
var1 = 10
print(hex(id(var1))) 

var1 = 100
print(hex(id(var1)))
```

You can't change an int object's value, so when you write var1 = 100 Python doesn't overwrite the memory holding 10 it creates a new int object for 100 and takes the name var1. 

```python
var2 = 100
print(hex(id(var2)))
```

CPython already has -5 to 256, since 100 falls in that range, var2 = 100 doesn't create a new object it just changes var2 to the same cached 100 object that var1 was already using.

 #  1b 

 ### 0xb45318    H (str1[0]) 
 ### 0xb45888    e (str1[1]) 
 ### 0xb459d8    l (str1[2]) 
 ### 0xb459d8    l (str1[3]) 
 ### 0xb45a68    o (str1[4]) 
 ### 0xb455e8    W (str2[0]) 
 ### 0xb45a68    o (str2[1]) 
 ### 0xb45af8    r (str2[2]) 
 ### 0xb459d8    l (str2[3]) 
 ### 0xb45858    d (str2[4]) 

 #  2a 
dogcat,
the dog chases the cat,
dogdogdogdog,

 #  2b 
```python
x = 50
x = x + 1
```

 #  3a 
a. hello = "hello"  Valid just assigning hello to the str version of hello

b. _var = 100 Valid underscores are ok

c. !var_1 = 200   SyntaxError, cannot start with exclamation

d. print = "print me"  Runs, but it would fail if you wanted to print something

e. False = 0 SyntaxError, cannot assign things to False, True, or None
