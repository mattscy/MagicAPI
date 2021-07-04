# CreateObject

This function finds an instance in your "Objects" folder with the given name and turns it into an object. The type of instance will determine which kind of object it becomes:

- Instances that are a `BasePart` will return an object of the `Part` class.
- Instances that are a `Model` will
    - Return an object of the `Character` class if the instance contains a `Humanoid`.
    - Return an object of the `Model` class otherwise.

The `Part`, `Character` and `Model` classes all inherit from the [`Object`][obj] class.

## Parameters
| Name | Type | Default | Description |
| - | - | - | - |
| `name` | `string` | | The name of the object that you want to create, which will be found in your "Objects" folder. |
| `relativeTo` | [`Object`][obj] | `Magic:GetMyCharacter()` | The new object will be created at an offset from this object. |
| `offset` | `Vector3` or `CFrame` | An offset that places the object in front of `relativeTo`. | Determines how far away the newly created object is placed from `relativeTo`. The magnitude will be clamped at 50.

## Returns
| Return Type | Summary |
| - | - |
| [`Object`][obj] | The object that was created from the instance. |

[obj]: ../../object/

## Mana Cost
Creating any object has a base cost of 50 mana. As well as this, creating larger objects will be more expensive, although objects with a size that is less than 1 will not be cheaper than objects with a size of 1. Objects that are created further away than 20 studs from `relativeTo` also have an additional cost.
```lua
local cost = 50 + math.max(1, object:GetSize())*10
local offsetDistance = 0
if offset then
    if type(offset) == "Vector3" then
        offsetDistance = offset.Magnitude
    elseif type(offset) == "CFrame" then
        offsetDistance = offset.Position.Magnitude
    end
end
cost += math.max(0, offsetDistance - 20)*10
return cost
```