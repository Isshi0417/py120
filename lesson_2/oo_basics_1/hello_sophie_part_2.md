# Hello, Sophie! (Part 2)
Using the code from the previous exercise, move the greeting from the `__init__` method to an instance method named `greet` that prints a
greeting when invoked. Make sure you write some code that invokes the method.

```python
class Cat:
    def __init__(self, name):
        self.name = name
        print(f"Hello! My name is {self.name}!")

kitty = Cat('Sophie')
kitty.greet()
```

## Solution
```python
class Cat:
    def __init__(self, name):
        self.name = name

    def greet(self):
        print(f"Hello! My name is {self.name}!")
```
