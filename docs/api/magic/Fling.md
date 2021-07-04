# Magic:Fling
Fling can be used to set the velocity of an object instantaneously rather than applying a continuous force. If another continuous force is being applied to the object (e.g. if the object was being moved with `Magic:SetVelocity`), setting the velocity in this way would ordinarily do nothing. However, the `duration` parameter can be used to override such other forces for an amount of time.

## Parameters
| Name | Type | Default | Description |
| - | - | - | - |
| `object` | [`Object`][obj] | | The object you want to fling. |
| `velocity` | `Vector3` | | The velocity you want the object to have. |
| `duration` | `float` | 0 | The duration that you want to override all other forces for. Must be between 0 and 10.

## Mana Cost
Larger objects and higher velocities cost more mana. Flinging enemy objects is 10x more expensive, and the `duration` parameter only affects the cost when flinging enemy objects.
```lua
local cost = object:GetSize()*velocity.Magnitude*0.1
if object:IsEnemy() then
    cost = cost*10 + duration*50
end
return cost
```

[obj]: ../../object/