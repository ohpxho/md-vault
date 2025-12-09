# Laravel Notes - Sept. 09, 2025

## Routed model binding

- Injects model instances into the routes automatically based on the parameters passed.
- So, instead of passing an Id then querying to the database to retrieve the data, you can just pass the Id then get the instance automatically.

## Service Container

- An IOC
- Handles class dependencies via dependency injection

## Service Provider

## Invesion of Control(IOC)

- A design pattern that let external container handle dependencies instead of the actual class implementing it

```
BEFORE:
class OrderService {
    private $paymentProcessor;
    private $emailService;

    public function __construct() {
        // Class controls dependency creation
        $this->paymentProcessor = new StripePayment();
        $this->emailService = new MailgunService();
    }
}

AFTER:
class OrderService {
    private $paymentProcessor;
    private $emailService;

    public function __construct(PaymentInterface $payment, EmailInterface $email) {
        // Dependencies injected by container
        $this->paymentProcessor = $payment;
        $this->emailService = $email;
    }
}
```

- An external container will inject the implementation from the classes defined in the constructor

## Service Layer Pattern

-
