Dependency Inversion Principle - Exercise

Which of the following is DIP-compliant?

A.
```python
# Low-level module
class EmailNotificationService:
    def send_email(self, message):
        # Code to send an email

# Low-level module
class SMSNotificationService:
    def send_sms(self, message):
        # Code to send an SMS

# High-level module
class NotificationManager:
    def __init__(self):
        self.email_service = EmailNotificationService()
        self.sms_service = SMSNotificationService()

    def send_notification(self, message, method):
        if method == 'email':
            self.email_service.send_email(message)
        elif method == 'sms':
            self.sms_service.send_sms(message)
```

B.
```python
from abc import ABC, abstractmethod

# Abstraction (interface)
class NotificationService(ABC):
    @abstractmethod
    def send(self, message):
        pass

# Low-level module
class EmailNotificationService(NotificationService):
    def send(self, message):
        # Code to send an email

# Low-level module
class SMSNotificationService(NotificationService):
    def send(self, message):
        # Code to send an SMS

# High-level module
class NotificationManager:
    def __init__(self):
        self.notification_service = None

    def set_notification_service(self, service):
        self.notification_service = service

    def send_notification(self, message):
        if self.notification_service:
            self.notification_service.send(message)
        else:
            raise ValueError("Notification service not set.")
```

Answer: B