# Magic:Fling
Fling can be used to set the velocity of an object instantaneously rather than applying a continuous force. If another continuous force is being applied to the object (e.g. if the object was being moved with `Magic:SetVelocity`), setting the velocity in this way would ordinarily do nothing. However, the `duration` parameter can be used to override such other forces for an amount of time.

## Parameters
| Name | Type | Default | Description |
| - | - | - | - |
| `object` | [`Object`][obj] | | The name of the object that you want to create, which will be found in your "Objects" folder. |
| `relativeTo` | `Vector3` | `Magic:GetMyCharacter()` | The new object will be created at an offset from this object. |
| `offset` | `float` | An offset that places the object in front of `relativeTo`. | Determines how far away the newly created object is placed from `relativeTo`.

## Mana
Larger objects and higher velocities cost more mana.
```lua
local cost = object:GetSize()*velocity.Magnitude
if object:IsEnemy() then
    cost *= 2
end
return cost
```

[obj]: ../../object/