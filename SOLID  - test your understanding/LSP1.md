Liskov Substitution Principle - Exercise

which if the following is Liskov Subsitituion Principle compliant?

A. 
```python
class Bird:
    def fly(self):
        pass

class Sparrow(Bird):
    def fly(self):
        print("Sparrow can fly")

class Ostrich(Bird):
    def fly(self):
        print("Ostrich can't fly")

def make_bird_fly(bird):
    bird.fly()

# Using LSP, we can substitute Sparrow and Ostrich objects for Bird
sparrow = Sparrow()
ostrich = Ostrich()

make_bird_fly(sparrow)  # Outputs: Sparrow can fly
make_bird_fly(ostrich)  # Outputs: Ostrich can't fly
```

B.
```python
class Bird:
    def fly(self):
        pass

class Sparrow(Bird):
    def fly(self):
        print("Sparrow can fly")

class Ostrich(Bird):
    def fly(self):
        print("Ostrich can't fly")

class Penguin(Bird):
    def swim(self):
        print("Penguin can swim")

def make_bird_fly(bird):
    bird.fly()

# Using LSP, we can substitute Sparrow, Ostrich, and Penguin objects for Bird
sparrow = Sparrow()
ostrich = Ostrich()
penguin = Penguin()

make_bird_fly(sparrow)  # Outputs: Sparrow can fly
make_bird_fly(ostrich)  # Outputs: Ostrich can't fly
make_bird_fly(penguin)  # Raises an AttributeError since penguin doesn't have a 'fly' metho
```
Answer: A