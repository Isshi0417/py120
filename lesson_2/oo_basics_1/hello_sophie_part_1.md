# Hello, Sophie! (Part 1)
Using the code from the previous exercise, add a parameter to `__init__` that provides a name for the `Cat` object.
Use an instance variable to print a greeting with the provided name. (You can remove the code that displays `I'm a cat!'.)

```python
class Cat:
    def __init__(self):
        print("I'm a cat!")

kitty = Cat('Sophie')
```

## Solution
```python
class Cat:
    def __inist__(self, name):
        self.name = name
        print(f"Hello, {self.name}!")
```
