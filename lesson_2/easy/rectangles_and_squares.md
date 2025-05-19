# Rectangles and Squares

Give nthe calss from the previous problem:

```python
class Rectangle:
    def __init__(self, width, height):
        self._width = width
        self._height = height

    @property
    def width(self):
        return self._width

    @property
    def height(self):
        return self._height

    @property
    def area(self):
        return self._width * self._height
```

Write a class called `Square` that inherits from the `Rectangle` class. 
The `Square` class is used like this:

```python
square = Square(5)
print(square.area == 25)      # True
```

# Solution

```python
class Square(Rectangle):
    def __init__(self, side_length):
        super().area(side_length, side_length)
```