# Rectangle

Create a `Rectangle` class whose initializer takes two arguments that represent the rectangle's width 
and height, respectively. Use the following code to test your solution:

```python
rect = Rectangle(4, 5)

print(rect.width == 4)        # True
print(rect.height == 5)       # True
print(rect.area == 20)        # True
```

# Solution

```python
class Rectangle(width, height):
    self.width = width
    self.height = height
    
    @property
    def width(self):
        return self.width
    
    @ property
    def height(self):
        return self.height
    
    @property
    def area(self):
        return self.width * self.height
```