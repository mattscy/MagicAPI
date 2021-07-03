# Object
All objects that you can manipulate with your magic are inherited from the [`Object`][obj] class. Models, parts and characters are all examples of objects that you can use magic on. An object can either be classified as "friendly" if it belongs to you or one of your teammates, "enemy" if it belongs to a player on another team, or "neutral" otherwise.

After a certain amount of time passes, an object will expire, and you can no longer call its methods or use it in the [`Magic`][mag] class. The lifetime of an object is different depending on how it is obtained:

- If obtained from the [`Magic:GetObject`](../magic/GetObject/) function, the object will expire after any yield.
- If obtained from the [`Magic:GetLingeringObject`](../magic/GetLingeringObject/) function, the object will expire after the returned subscription is cancelled.
- Any objects will expire after they are destroyed.
- If the object belongs to you, it will not expire until it is destroyed.

However, some [`HitDetails`][hit] objects have an associated lifetime that will be used instead of the above conditions. For example, the [`HitDetails`][hit] that is obtained from [`Magic:GetSphereDetectionSignal`](../magic/GetSphereDetectionSignal/) when `entered` is true will give an object that expires after the object leaves the radius, rather than after an amount of time.

## Functions
`float `[`GetSize`](./GetSize/)`()`  
Returns the size of the object based on its diagonal width.

`Vector3 GetDimensions()`  
Returns the length, height and width of the object.

`Vector3 GetVelocity()`

`CFrame GetCFrame()`

`string GetName()`

`bool IsType(string type)`

`bool IsExpired()`

`bool IsEnemy()`

`bool IsFriendly()`

`bool IsNeutral()`

`bool IsMine()`

[`Object`][obj]` GetSubObject(string name)`  
Gets a sub-object thats inside of the object (e.g. a part that is inside a model).

`AnimationTrack LoadAnimation(int animationID)`

## Events
`Expiring -> (bool wasDestroyed)`

`Touched -> (`[`HitDetails`][hit]` touchedObjectDetails)`

[obj]: ../object/
[hit]: ../hitdetails/
[mag]: ../magic/