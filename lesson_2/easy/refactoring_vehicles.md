# Refactoring Vehicles

Consider the following classes:

```python
class Car:
    def __init__(self, make, model):
        self.make = make
        self.model = model

    def get_wheels(self):
        return 4

    def info(self):
        return f"{self.make} {self.model}"

class Motorcycle:
    def __init__(self, make, model):
        self.make = make
        self.model = model

    def get_wheels(self):
        return 2

    def info(self):
        return f"{self.make} {self.model}"

class Truck:
    def __init__(self, make, model, payload):
        self.make = make
        self.model = model
        self.payload = payload

    def get_wheels(self):
        return 6

    def info(self):
        return f"{self.make} {self.model}"
```

Refactor these classes so they all use a common superclass, and inherit behavior as needed.

# Solution

```python
class Vehicle():
    def __init__(self, make, model):
        self.make = make
        self.model = model

    def info(self):
        return f"{self.make} {self.model}"
    
class Car(Vehicle):
    def get_wheels(self):
        return 4

class Motorcycle(Vehicle):
    def get_wheels(self):
        return 2
    
class Truck(Vehicle):
    def __init__(self, make, model, payload):
        super().__init__(make, model)
        self.payload = payload

    def get_wheels(self):
        return 6
```