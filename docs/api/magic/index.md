# Magic
The `Magic` class is the core class of the system. It manages your mana and provides all the functions that you can use to manipulate objects in the game. Mana is a measurement of your magical potential, similarly to how stamina is a measurement of physical potential. You can spend mana to achieve all kinds of magical effects.

Most of the functions in the `Magic` class cost an amount of mana depending on the arguments that you give. For example, the [`Magic:Fling`](./Fling/) function can be used to fling an object by temporarily setting its velocity. However, using a velocity with a larger magnitude will cost more mana. It is also important keep in mind that using functions on enemy objects is often more expensive than using the same functions on friendly objects.

This class also lets you retrieve the Character object that represents your character using the `Mana:GetMyCharacter` function. Your script will only run after your character is completely loaded every time you respawn, so you don't have to worry about waiting for anything.

## Functions
`Character GetMyCharacter()`  
Returns an object that represents your character.

[`Object`][obj]` CreateObject(string name, [`[`Object`][obj]` relativeTo, (Vector3|CFrame) offset])`  
Creates a new object from a name.

[`Object`][obj]` GetObject(`[`HitDetails`][hit]` hitObjectDetails)`  
Returns an object from a HitDetails that expires immediately.

[`Subscription`][sub]`, `[`Object`][obj]` GetLingeringObject(HitDetails hitObjectDetails)`  
Returns an object from a HitDetails that expires after the subscription is cancelled.

`void ChargeDamage(`[`Object`][obj]` object, int amount)`  
Charges an object with an amount of damage.

[`Subscription`][sub]` Follow(`[`Object`][obj]` object, Object target, (Vector3|CFrame) offset)`  
Makes an object follow a target object at a constant offset.

[`Subscription`][sub]` SetVelocity(`[`Object`][obj]` object, Vector3 velocity)`  
Gives an object a constant velocity until the subscription is cancelled.

[`Subscription`][sub]` Watch(`[`Object`][obj]` pointing, (`[`Object`][obj]`|Mouse) target, [(Vector3|CFrame) targetOffset])`  
Makes an object point towards another object until the subscription is cancelled.

`void LookAt(`[`Object`][obj]` pointing, (`[`Object`][obj]`|Mouse) target, [(Vector3|CFrame) targetOffset])`  
Makes an object point towards another object.

`void `[`Fling`](./Fling/)`(`[`Object`][obj]` object, Vector3 velocity, [float duration])`  
Gives an object an instantaneous thrust that overrides all other forces until the duration passes.

[`Subscription`][sub]`, RBXScriptSignal -> (bool entered, `[`HitDetails`][hit]` detectedDetails)  `[`GetSphereDetectionSignal`](./GetSphereDetectionSignal/)`(`[`Object`][obj]` detecting, float radius)`  
Returns an event that fires when something enters the radius of an object until the subscription is cancelled.

`void Overdrive(bool enabled)`  
Allows health to be spent as mana when enabled.

## Events
`ManaChanged -> (int currentMana, int maxMana)`

[obj]: ../object/
[sub]: ../subscription/
[hit]: ../hitdetails/