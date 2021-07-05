# Magic:Resize

The resize function lets you transition the object from one size to another in an amount of time. A `TweenInfo` instance can be used instead of a number for the `resizeInfo` parameter if you want to customise the easing style and direction of the transition.

!!! warning
    Resizing `Model` objects may not work as expected unless the new size has the same length:height:width ratio as the original size.

## Parameters
| Name | Type | Default | Description |
| - | - | - | - |
| `object` | [`Object`][obj] | | The object that you are resizing. |
| `resizeInfo` | `float` or `TweenInfo` | 1 | The time you want the resize to take. If a `TweenInfo` is used, the `DelayTime`, `RepeatCount` and `Reverses` properties will be ignored. |

[obj]: ../../Object/