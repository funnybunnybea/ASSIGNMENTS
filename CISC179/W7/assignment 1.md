# Python OOP Exercises

## 1. CountingStack

```python
class Stack:
    def __init__(self):
        self.__stk = []

    def push(self, val):
        self.__stk.append(val)

    def pop(self):
        val = self.__stk[-1]
        del self.__stk[-1]
        return val


class CountingStack(Stack):
    def __init__(self):
        Stack.__init__(self)
        self.__counter = 0

    def get_counter(self):
        return self.__counter

    def pop(self):
        self.__counter += 1
        return Stack.pop(self)


stk = CountingStack()
for i in range(100):
    stk.push(i)
    stk.pop()
print(stk.get_counter())  # 100
```

## 2. Queue and SuperQueue

```python
class QueueError(IndexError):
    pass


class Queue:
    def __init__(self):
        self.__queue = []

    def put(self, elem):
        self.__queue.insert(0, elem)

    def get(self):
        if not self.__queue:
            raise QueueError
        return self.__queue.pop()

    def _size(self):
        return len(self.__queue)


class SuperQueue(Queue):
    def isempty(self):
        return self._size() == 0


que = SuperQueue()
que.put(1)
que.put("dog")
que.put(False)
for i in range(4):
    if not que.isempty():
        print(que.get())  # 1, dog, False
    else:
        print("Queue empty")
```

## 3. Timer

```python
def two_digits(n):
    return str(n).zfill(2)


class Timer:
    def __init__(self, hours=0, minutes=0, seconds=0):
        self.__total = hours * 3600 + minutes * 60 + seconds

    def __str__(self):
        h, rest = divmod(self.__total, 3600)
        m, s = divmod(rest, 60)
        return two_digits(h) + ":" + two_digits(m) + ":" + two_digits(s)

    def next_second(self):
        self.__total = (self.__total + 1) % 86400

    def prev_second(self):
        self.__total = (self.__total - 1) % 86400


timer = Timer(23, 59, 59)
print(timer)  # 23:59:59
timer.next_second()
print(timer)  # 00:00:00
timer.prev_second()
print(timer)  # 23:59:59
```

## 4. Weeker

```python
class WeekDayError(Exception):
    pass


class Weeker:
    __names = ['Mon', 'Tue', 'Wed', 'Thu', 'Fri', 'Sat', 'Sun']

    def __init__(self, day):
        if day not in Weeker.__names:
            raise WeekDayError
        self.__current = Weeker.__names.index(day)

    def __str__(self):
        return Weeker.__names[self.__current]

    def add_days(self, n):
        self.__current = (self.__current + n) % 7

    def subtract_days(self, n):
        self.__current = (self.__current - n) % 7


try:
    weekday = Weeker('Mon')
    print(weekday)  # Mon
    weekday.add_days(15)
    print(weekday)  # Tue
    weekday.subtract_days(23)
    print(weekday)  # Sun
    weekday = Weeker('Monday')
except WeekDayError:
    print("Sorry, I can't serve your request.")
```
