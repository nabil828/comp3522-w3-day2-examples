Law of Demeter - test your understanding - Exercise

which of the following is not a violation of the Law of Demeter?

A.
```python
class Owner:
    def __init__(self):
        self.pet = Dog()

class Dog:
    def fetch(self, ball):
        print("Fetching the ball")

class Ball:
    pass

owner = Owner()
owner.pet.fetch(Ball())  # Non-compliant, violates LoD
```


B.
```python
class Owner:
    def __init__(self):
        self.pet = Dog()

    def askPetToFetch(self, ball):
        self.pet.fetch(ball)

class Dog:
    def fetch(self, ball):
        print("Fetching the ball")

class Ball:
    pass

owner = Owner()
owner.askPetToFetch(Ball())  # Compliant with LoD
```