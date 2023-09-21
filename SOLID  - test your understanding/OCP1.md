Open-Closed Principle - Exercise 

Which of the following is OCP-complikant

A. 
```python
class Shape:
    def __init__(self, shape_type):
        self.shape_type = shape_type
    
    def area(self):
        if self.shape_type == "circle":
            return 3.14 * self.radius * self.radius
        elif self.shape_type == "square":
            return self.side * self.side
        # New shape types require modifying this class, violating OCP.

class Circle(Shape):
    def __init__(self, radius):
        super().__init__("circle")
        self.radius = radius
    
class Square(Shape):
    def __init__(self, side):
        super().__init__("square")
        self.side = side
```

B. 
```python
class Shape:
    def area(self):
        pass

class Circle(Shape):
    def __init__(self, radius):
        self.radius = radius
    
    def area(self):
        return 3.14 * self.radius * self.radius

class Square(Shape):
    def __init__(self, side):
        self.side = side
    
    def area(self):
        return self.side * self.side

# New functionality added without modifying existing code

class Triangle(Shape):
    def __init__(self, base, height):
        self.base = base
        self.height = height
    
    def area(self):
        return 0.5 * self.base * self.height
```


Answer: B