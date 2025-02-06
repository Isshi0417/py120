# What are You?
Using the code from the previous exercise, add a __init__ method that prints `I'm a cat!` when a new `Cat` object is instantiated.

```python
class Cat:
    pass

kitty = Cat()
```

## Solution
```python
class Cat:
    def __init__(self):
        print("I'm a cat!")
```
