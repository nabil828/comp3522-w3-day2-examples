Interface Segregation Principle

Which of the folowing is ISP-compliant?

A.
```python
from abc import ABC, abstractmethod

# Define smaller interfaces for device functionalities
class Powerable(ABC):
    @abstractmethod
    def power_on(self):
        pass

    @abstractmethod
    def power_off(self):
        pass

class Connectable(ABC):
    @abstractmethod
    def connect(self):
        pass

    @abstractmethod
    def disconnect(self):
        pass

# Implement classes adhering to the appropriate interfaces
class Laptop(Powerable, Connectable):
    def power_on(self):
        print("Laptop is powering on.")

    def power_off(self):
        print("Laptop is powering off.")

    def connect(self):
        print("Laptop is connecting to the internet.")

    def disconnect(self):
        print("Laptop is disconnecting from the internet.")

class Lamp(Powerable):
    def power_on(self):
        print("Lamp is lighting up.")

    def power_off(self):
        print("Lamp is turning off.")

# Client code
laptop = Laptop()
lamp = Lamp()

laptop.power_on()
laptop.connect()
laptop.disconnect()
laptop.power_off()

lamp.power_on()
lamp.power_off()

```



B.
```python
from abc import ABC, abstractmethod

# Non-compliant version with a monolithic interface
class ElectronicDevice(ABC):
    @abstractmethod
    def power_on(self):
        pass

    @abstractmethod
    def power_off(self):
        pass

    @abstractmethod
    def connect(self):
        pass

    @abstractmethod
    def disconnect(self):
        pass

class Laptop(ElectronicDevice):
    def power_on(self):
        print("Laptop is powering on.")

    def power_off(self):
        print("Laptop is powering off.")

    def connect(self):
        print("Laptop is connecting to the internet.")

    def disconnect(self):
        print("Laptop is disconnecting from the internet.")

class Lamp(ElectronicDevice):
    def power_on(self):
        print("Lamp is lighting up.")

    def power_off(self):
        print("Lamp is turning off.")

# Client code
laptop = Laptop()
lamp = Lamp()

laptop.power_on()
laptop.connect()
laptop.disconnect()
laptop.power_off()

lamp.power_on()
lamp.power_off()

```



Answer: A