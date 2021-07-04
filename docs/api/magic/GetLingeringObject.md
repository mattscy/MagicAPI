# Magic:GetLingeringObject

This function is an alternative to the [`Magic:GetObject`](../GetObject/) function that allows for a continuous reference to the object that you retrieve from a [`HitDetails`][hit]. The reference to the object will expire once the returned subscription expires.

## Parameters
| Name | Type | Default | Description |
| - | - | - | - |
| `hitObjectDetails` | [`HitDetails`][hit] | | The [`HitDetails`][hit] of the object that you have detected. |

## Returns
| Return Type | Summary |
| - | - |
| [`Subscription`][sub] | When this subscription is cancelled, the returned object will expire. |
| [`Object`][obj] | The object that you retrieve from the [`HitDetails`][hit]. This object will expire after the returned subscription is cancelled. |

## Mana Cost
There is no immediate cost for getting a lingering object. The cost rate of the subscription is determined by the type of the detected object.
```lua
local cost = 0
local subCost
if hitObjectDetails:IsMine() then
    subCost = 0
elseif hitObjectDetails:IsFriendly() then
    subCost = 1
elseif hitObjectDetails:IsEnemy() then
    subCost = 10
end
return cost, subCost
```

[hit]: ../../hitdetails/
[obj]: ../../object/
[sub]: ../../subscription/