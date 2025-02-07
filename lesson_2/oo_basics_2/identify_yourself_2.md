# Identify Yourself (Part 2)
Update the following code so that it prints `I'm Sophie!` when it invokes `print(kitty)`.

```python
class Cat:
    def __init__(self, name):
        self._name = name

    @property
    def name(self):
        return self._name

# Comments show expected output
kitty = Cat('Sophie')
print(kitty)        # I'm Sophie!
```

## Solution
```python
def __str__(self):
    print(f"I'm {self.name}!")
```
