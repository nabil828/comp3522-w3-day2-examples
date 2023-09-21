Dependency Inversion Principle - Exercise

Which of the following is DIP-compliant?

A.
```python
# Low-level module
class PaymentProcessor:
    def process_payment(self, amount):
        # Logic to process payment
        pass

# High-level module
class OrderService:
    def __init__(self):
        self.payment_processor = PaymentProcessor()

    def checkout(self, order_total):
        self.payment_processor.process_payment(order_total)

# Usage
order_service = OrderService()
order_service.checkout(100)
```

B.
```python
# Compliant version

# Abstraction (interface)
class PaymentProcessor:
    def process_payment(self, amount):
        pass

# Low-level module
class PayPalProcessor(PaymentProcessor):
    def process_payment(self, amount):
        # Logic to process payment via PayPal
        pass

class StripeProcessor(PaymentProcessor):
    def process_payment(self, amount):
        # Logic to process payment via Stripe
        pass

# High-level module
class OrderService:
    def __init__(self, payment_processor):
        self.payment_processor = payment_processor

    def checkout(self, order_total):
        self.payment_processor.process_payment(order_total)

# Usage
paypal_processor = PayPalProcessor()
order_service_paypal = OrderService(paypal_processor)
order_service_paypal.checkout(100)

stripe_processor = StripeProcessor()
order_service_stripe = OrderService(stripe_processor)
order_service_stripe.checkout(200)

```

Answer: B