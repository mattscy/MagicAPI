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
| `relativeTo` | `Vector3` | `Magic:GetMyCharacter()` | The new object will be created at an offset from this object. |
| `offset` | `float` | An offset that places the object in front of `relativeTo`. | Determines how far away the newly created object is placed from `relativeTo`.

## Returns
| Return Type | Summary |
| - | - |
| [`Object`][obj] | The object that was created from the instance. |

[obj]: ../../object/