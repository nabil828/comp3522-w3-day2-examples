Interface Segregation Principle

Which of the folowing is ISP-compliant?

A.
```python
# Define two smaller interfaces for Manual Labor and Office Work
class ManualLaborWorker:
    def do_manual_labor(self):
        pass

class OfficeWorker:
    def do_office_work(self):
        pass

# Implement classes that adhere to the appropriate interfaces
class ConstructionWorker(ManualLaborWorker):
    def do_manual_labor(self):
        print("Construction worker is doing manual labor.")

class Programmer(OfficeWorker):
    def do_office_work(self):
        print("Programmer is doing office work.")

# Client code
construction_worker = ConstructionWorker()
programmer = Programmer()

construction_worker.do_manual_labor()
programmer.do_office_work()

```



B.
```python
# monolithic interface
class Worker:
    def do_manual_labor(self):
        pass

    def do_office_work(self):
        pass

class ConstructionWorker(Worker):
    def do_manual_labor(self):
        print("Construction worker is doing manual labor.")

class Programmer(Worker):
    def do_office_work(self):
        print("Programmer is doing office work.")

# Client code
construction_worker = ConstructionWorker()
programmer = Programmer()

construction_worker.do_manual_labor()
programmer.do_office_work()
```




C. 
```python
from abc import ABC, abstractmethod

# Monolithic ABC
class Worker(ABC):
    @abstractmethod
    def do_manual_labor(self):
        pass

    @abstractmethod
    def do_office_work(self):
        pass

class ConstructionWorker(Worker):
    def do_manual_labor(self):
        print("Construction worker is doing manual labor.")

    def do_office_work(self):
        pass

class Programmer(Worker):
    def do_office_work(self):
        print("Programmer is doing office work.")
        
    def do_manual_labor(self):
        pass
```

Answer: A