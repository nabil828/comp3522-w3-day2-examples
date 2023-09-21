Liskov Substitution Principle - Exercise

which if the following is Liskov Subsitituion Principle compliant?
A. 
```python
class Shape:
    def area(self):
        pass

class Rectangle(Shape):
    def __init__(self, width, height):
        self.width = width
        self.height = height

    def area(self):
        return self.width * self.height

class Circle(Shape):
    def __init__(self, radius):
        self.radius = radius

    def area(self):
        return 3.14 * self.radius * self.radius

def calculate_area(shape):
    return shape.area()

# Using LSP, we can substitute Rectangle and Circle objects for Shape
rectangle = Rectangle(5, 4)
circle = Circle(3)

print(calculate_area(rectangle))  # Outputs: 20
print(calculate_area(circle))     # Outputs: 28.26 (approximately)

```

B.
```python
class Shape:
    def area(self):
        pass

class Rectangle(Shape):
    def __init__(self, width, height):
        self.width = width
        self.height = height

    def area(self):
        return self.width * self.height

class Circle(Shape):
    def __init__(self, radius):
        self.radius = radius

def calculate_area(shape):
    return shape.area()

# Using LSP, we can substitute Rectangle and Circle objects for Shape
rectangle = Rectangle(5, 4)
circle = Circle(3)

print(calculate_area(rectangle))  # Outputs: 20
print(calculate_area(circle))     # Raises AttributeError since Circle doesn't have an 'area' method
```


Answer: A