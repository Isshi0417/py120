# Hello, Chloe!
Using the following code, add an instance method named `rename` that renames `kitty` when invoked.

```python
class Cat:
    def __init__(self, name):
        self._name = name

    @property
    def name(self):
        return self._name

    @name.setter
    def name(self, value):
        self._name = value

# Comments show expected output
kitty = Cat('Sophie')
print(kitty.name)             # Sophie
kitty.rename('Chloe')
print(kitty.name)             # Chloe
```

## Solution
```python
def rename(self, name):
    self._name = name
```
