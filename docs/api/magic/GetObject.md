# Magic:GetObject
This function allows you to convert a [`HitDetails`][hit] into an object that you can interact with. The object returned from this function will usually expire immediately after any yield (the exception to this is the [`HitDetails`][hit] from the [`Magic:GetSphereDetectionSignal`](../GetSphereDetectionSignal/) function). This means that any effect that you want to apply to the object must be applied immediately after using `Magic:GetObject`. If you instead want a continuous reference to an object, consider using the [`Magic:GetLingeringObject`](../GetLingeringObject/) function instead.

## Parameters
| Name | Type | Default | Description |
| - | - | - | - |
| `hitObjectDetails` | [`HitDetails`][hit] | | The [`HitDetails`][hit] of the object that you have detected. |

## Returns
| Return Type | Summary |
| - | - |
| [`Object`][obj] | The object that you retrieve from the [`HitDetails`][hit]. This object will expire after any yield. |

## Mana Cost
This function does not currently cost any mana.
```lua
local cost = 0
return cost
```

[obj]: ../../object/
[hit]: ../../hitdetails/