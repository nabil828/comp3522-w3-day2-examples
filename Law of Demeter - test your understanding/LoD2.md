Law of Demeter - test your understanding - Exercise

which of the following is not a violation of the Law of Demeter?

A.
```python
class Wallet:
    def __init__(self):
        self.balance = 0

    def add_money(self, amount):
        self.balance += amount

class Person:
    def __init__(self):
        self.wallet = Wallet()

    def spend_money(self, amount):
        self.wallet.balance -= amount

# Non-compliant: Main class is directly accessing the balance of a person's wallet.
person = Person()
person.wallet.add_money(1000)
person.wallet.balance -= 500
print(f"Remaining balance: {person.wallet.balance}")

```


B.
```python
class Wallet:
    def __init__(self):
        self.balance = 0

    def add_money(self, amount):
        self.balance += amount

    def spend_money(self, amount):
        if self.balance >= amount:
            self.balance -= amount
            return True
        return False

class Person:
    def __init__(self):
        self.wallet = Wallet()

    def spend_money(self, amount):
        return self.wallet.spend_money(amount)

# Compliant with LoD: Main class uses the spend_money method provided by the Person class.
person = Person()
person.wallet.add_money(1000)
if person.spend_money(500):
    print("Purchase successful")
    print(f"Remaining balance: {person.wallet.balance}")
else:
    print("Insufficient funds")

```

Answer: B
