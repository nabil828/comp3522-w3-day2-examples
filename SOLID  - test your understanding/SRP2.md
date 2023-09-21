Single Responsibility Principle - Exercise

Which of the following is SRP-compliant?


- A
```python 
class UserSettings:
    def __init__(self, user):
        self.user = user

    def change_settings(self, settings):
        if self.verify_credentials():
            pass

    def verify_credentials(self):
        pass
```

- B
```python
class UserAuth:
    def __init__(self, user):
        self.user = user

    def verify_credentials(self):
        pass

class UserSettings:
    def __init__(self, user):
        self.user = user
        self.auth = UserAuth(user)

    def change_settings(self, settings):
        if self.auth.verify_credentials():
            pass
```


Answer: B