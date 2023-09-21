
Single Responsibility Principle - Exercise 

Which of the following is SRP-compliant?

- A
```python
class Book:
    def __init__(self, title, author, ISBN):
        self.title = title
        self.author = author
        self.ISBN = ISBN

    def get_book_info(self):
        # Code to retrieve book information from a database
        pass

    def save_book_info(self):
        # Code to save book information to a database
        pass

    def print_book(self):
        # Code to print book details
        pass
```

- B
```python
class Book:
    def __init__(self, title, author, ISBN):
        self.title = title
        self.author = author
        self.ISBN = ISBN

class BookDatabase:
    def get_book_info(self, book):
        # Code to retrieve book information from a database
        pass

    def save_book_info(self, book):
        # Code to save book information to a database
        pass

class BookPrinter:
    def print_book(self, book):
        # Code to print book details
        pass
```

Anwer: B