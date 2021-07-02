# HitDetails
A `HitDetails` instance is given whenever you detect another object, such as through the `Touched` event. The purpose of this class is to let you check the details of an object that you have detected before you decide to pay for a reference to it. If you do decide that you want a reference, you can pay for the object with the `Magic:GetObject` or `Magic:GetLingeringObject` methods. For balancing reasons, `HitDetails` instances expire as soon as there is any yield, so you can't wait before getting an object from a `HitDetails`.

## Functions
`bool IsEnemy()`

`bool IsFriendly()`

`bool IsTerrain()`

`bool IsMine()`

`bool IsType(string type)`