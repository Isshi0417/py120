# Default Person
Create a class named `Person`. When you instantitate a `Person` object, you should pass in one argument that contains the person's name.
If no arguments are given, the `Person` object should be instantiated with a name of `"John Doe"`.

## Solution
```python
class Person:
    def __init__(self, name):
        if len(name) < 1:
            self._name = "John Doe"

        self._name = name
```
