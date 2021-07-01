# Magic
The `Magic` class is the core class of the system. It manages your mana and provides all the functions that you can use to manipulate objects in the game. Mana is a measurement of your magical potential, similarly to how stamina is a measurement of physical potential. You can spend mana to achieve all kinds of magical effects.

Most of the functions in the `Magic` class cost an amount of mana depending on the arguments that you give. For example, the `Magic:Fling` function can be used to fling an object by temporarily setting its velocity. However, using a velocity with a larger magnitude will cost more mana. It is also important keep in mind that using functions on enemy objects is often more expensive than using the same functions on friendly objects.

This class also lets you retrieve the Character object that represents your character using the `Mana:GetMyCharacter` function. Your script will only run after your character is completely loaded every time you respawn, so you don't have to worry about waiting for anything.

## Functions



| `Character` [`GetMyCharacter()`](../GetMyCharacter.md) |
| - |
| Gets the character  |

```
Object CreateObject(string name, [Object relativeTo, (Vector3|CFrame) offset])
```
```
Object GetObject(HitDetails hitObjectDetails)
```
```
Subscription, Object GetLingeringObject(HitDetails hitObjectDetails)
```
```
void ChargeDamage(Object object, int amount)
```
```
Subscription Follow(Object object, Object target, (Vector3|CFrame) offset)
```
```
Subscription SetVelocity(Object object, Vector3 velocity) 
```
```
Subscription Watch(Object pointing, (Object|Mouse) target, [(Vector3|CFrame) targetOffset])
```
```
void LookAt(Object pointing, (Object|Mouse) target, [(Vector3|CFrame) targetOffset])
```
```
void Fling(Object object, Vector3 velocity, [float duration])
```
```
Subscription, RBXScriptSignal -> (bool entered, HitDetails detectedDetails) GetRadiusDetectionSignal(Object detecting, float radius)
```

## Events
```
ManaChanged -> (int currentMana, int maxMana)
```