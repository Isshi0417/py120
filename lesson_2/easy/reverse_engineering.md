# Reverse Engineering

Write a class such that the following code prints the results indicated by the comments:

```python
my_data = Transform('abc')
print(my_data.uppercase())              # ABC
print(Transform.lowercase('XYZ'))       # xyz
```

# Solution

```python
class Transform:
    def __init__(self, string):
        self.string = string

    def uppercase(self):
        return self.string.upper()
    
    @classmethod
    def lowercase(cls, string):
        return string.lower()
```