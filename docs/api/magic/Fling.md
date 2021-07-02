# Magic:Fling
Fling can be used to set the velocity of an object instantaneously rather than applying a continuous force. If another continuous force is being applied to the object (e.g. if the object was being moved with `Magic:SetVelocity`), setting the velocity in this way would ordinarily do nothing. However, the `duration` parameter can be used to override such other forces for an amount of time.

## Parameters
| Name | Type | Default | Description |
| - | - | - | - |
| `object` | [`Object`][obj] | | The object you want to fling. |
| `velocity` | `Vector3` | | The velocity you want the object to have. |
| `duration` | `float` | 0 | The duration that you want to override all other forces for.

## Mana
Larger objects and higher velocities cost more mana.
```lua
return object:GetSize()*velocity.Magnitude
```

[obj]: ../../object/