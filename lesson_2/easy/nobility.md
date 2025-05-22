# Nobility

Now tat we have a `WalkMixin` mix-in, we are given a new challenge. Apparently some of our users are nobility, and the regular way fo walking simply isn't good enough. Nobility struts.

We need a new class `Noble` that shows the title and name when `walk` is called. We also require access to `name` and `title`; they are needed for other purposes that we aren't showing here.

# Solution

```python
class WalkMixin:
    def walk(self):
        return f"{self} {self.gait()} forward"

class Person(WalkMixin):
    def __init__(self, name):
        self.name = name

    def gait(self):
        return "strolls"
    
    def __str__(self):
        return self.name

class Cat(WalkMixin):
    def __init__(self, name):
        self.name = name

    def gait(self):
        return "saunters"
    
    def __str__(self):
        return self.name

class Cheetah(WalkMixin):
    def __init__(self, name):
        self.name = name

    def gait(self):
        return "runs"
    
    def __str__(self):
        return self.name

class Noble(WalkMixin):
    def __init__(self, name, title):
        self.name = name
        self.title = title
    
    def gait(self):
        return "struts"

    def __str__(self):
        return f"{self.title} {self.name}"
```