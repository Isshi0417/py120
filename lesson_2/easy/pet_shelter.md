# Pet Shelter

Consider the following code:

```python
cocoa   = Pet('cat', 'Cocoa')
cheddar = Pet('cat', 'Cheddar')
darwin  = Pet('bearded dragon', 'Darwin')
kennedy = Pet('dog', 'Kennedy')
sweetie = Pet('parakeet', 'Sweetie Pie')
molly   = Pet('dog', 'Molly')
chester = Pet('fish', 'Chester')

phanson = Owner('P Hanson')
bholmes = Owner('B Holmes')

shelter = Shelter()
shelter.adopt(phanson, cocoa)
shelter.adopt(phanson, cheddar)
shelter.adopt(phanson, darwin)
shelter.adopt(bholmes, kennedy)
shelter.adopt(bholmes, sweetie)
shelter.adopt(bholmes, molly)
shelter.adopt(bholmes, chester)

shelter.print_adoptions()
print(f"{phanson.name} has {phanson.number_of_pets()} "
      "adopted pets.")
print(f"{bholmes.name} has {bholmes.number_of_pets()} "
      "adopted pets.")
```

Write the classes and methods that will be necessary to make this code run, and log the following output:

```
P Hanson has adopted the following pets:
a cat named Cocoa
a cat named Cheddar
a bearded dragon named Darwin

B Holmes has adopted the following pets:
a dog named Molly
a parakeet named Sweetie Pie
a dog named Kennedy
a fish named Chester

P Hanson has 3 adopted pets.
B Holmes has 4 adopted pets.
```

The order of the output does not matter, so long as all of the information is presented.

# Solution

```python
class Pet:
    def __init__(self, species, name):
        self._species = species
        self._name = name
    
    def info(self):
        print(f"a {self._species} named {self._name}")

class Owner:
    def __init__(self, name):
        self._name = name
        self.pets = []

    def add_pet(self, pet):
        self.pets.append(pet)

    def number_of_pets(self):
        return len(self.pets)
    
    def print_pets(self):
        for pet in self.pets:
            print(pet.info())

class Shelter:
    def __init__(self):
        self.owners = {}

    def adopt(self, owner, pet):
        owner.add_pet(pet)
        if owner._name not in self.owners:
            self.owners[owner._name] = owner

    def print_adoptions(self):
        for name, owner in self.owners.items():
            print(f"{name} has adopted the following pets: ")
            owner.print_pets()
            print("")
```