# Subscription
`Subscription` instances are returned from any function in the `Magic` class that charges mana at a continuous rate rather than a one-time payment. When a subscription is cancelled, you stop paying mana for that function, and the effect of the function is stopped. Subscriptions can be cancelled in one of four ways:
    1. You manually cancel the subscription with `Subscription:Cancel()`.
    2. If any of the objects you are using the function on expire, the subscription will be cancelled.
    3. If you don't have enough mana left to pay for a subscription, it will be cancelled.
    4. When you reuse the same function on the same object, it will cancel the previous subscription. In this case, the `overridden` parameter of `Subscription.Cancelled` will be set to true.

## Functions
```
void Cancel()
```
```
bool IsCancelled()
```
```
int GetRate()
```
```
int GetTotalSpent()
```
## Events
```
Cancelled -> (bool overridden)
```