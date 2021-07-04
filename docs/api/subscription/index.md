# Subscription
[`Subscription`][sub] instances are returned from any function in the [`Magic`][mag] class that charges mana at a continuous rate rather than a one-time payment. When a subscription is cancelled, you stop paying mana for that function, and the effect of the function is stopped. Subscriptions can be cancelled in one of four ways:  

1. You manually cancel the subscription with `Subscription:Cancel()`.
2. If any of the objects you are using the function on expire, the subscription will be cancelled. 
3. If your mana runs out, all active subscriptions will be cancelled.  
4. When you reuse the same function on the same object, it will cancel the previous subscription. In this case, the `overridden` parameter of `Subscription.Cancelled` will be set to true.

## Functions
`void Cancel()`  
Cancels the subscription, which ends the effect of the subscription and stops charging mana for the subscription.

`void CancelIn(duration)`  
Cancels the subscription after the duration passes. 

`bool IsCancelled()`

`int GetRate()`

`int GetTotalSpent()`

## Events
`Cancelled -> (bool overridden)`  
Fires when the subscription is cancelled for any reason. Overridden is true if it was cancelled by a new subscription that was created by the same function for the same object.

[sub]: ../subscription/
[mag]: ../magic/