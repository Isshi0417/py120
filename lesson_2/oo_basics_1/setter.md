# Setter
Using the code snippet provided below, add a setter method named `name`. Then, rename `kitty` to `'Luna'` and invoke `greet` again.

```python
class Cat:
    def __init__(self, name):
        self._name = name

    @property
    def name(self):
        return self._name

    def greet(self):
        print(f"Hello! My name is {self.name}!")

kitty = Cat('Sophie')
kitty.greet()
```

## Solution
```python
class Cat:
    def __init__(self, name):
        self._name = name

    @property
    def name(self):
        return self._name

    @name.setter
    def name(self, name):
        self._name = name

    def greet(self):
        print(f"Hello! My name is {self.name}!")

kitty.name = 'Luna'
kitty.greet()
```
