# Magic:GetSphereDetectionSignal
This function allows you to detect and use objects that are within a certain radius from a specified object. While the subscription is active, the returned `RBXScriptSignal` will fire for any object that enters or leaves the radius, giving you the [`HitDetails`][hit] of that object.

The [`HitDetails`][hit] that is provided when an object enters the radius is different to normal [`HitDetails`][hit]. You must use `Magic:GetObject` to get the object from this [`HitDetails`][hit] (as opposed to `Magic:GetLingeringObject`), and rather than expiring immediately, the object will only expire after it leaves the radius again. This allows you to use any object freely as long as it is within the radius of the detection sphere.

## Parameters
| Name | Type | Default | Description |
| - | - | - | - |
| `detecting` | [`Object`][obj] | | The position of this object is the centre of the detection sphere. |
| `radius` | `float` | | The radius of the detection sphere. |

## Returns
| Return Type | Summary |
| - | - |
| [`Subscription`][sub] | When this subscription is cancelled, the `RBXScriptSignal` will no longer fire. |
| `RBXScriptSignal` | This event will fire every time an object enters or leaves the radius of the sphere. If fired when the object enters, any object retrieved from the [`HitDetails`][hit] will expire when the object leaves the radius. If fired when the object leaves, the object retrieved from the [`HitDetails`][hit] will act normally. |

## Mana
Mana is charged at a rate while the subscription is active.

## Code Samples
The following code heals an object while it is within the detection sphere radius:
```lua
local detectSub, detectionSignal = Magic:GetSphereDetectionSignal(object)

detectionSignal:Connect(function(hitDetails, entered)
    if entered then
        local detectedObject = Magic:GetObject(hitDetails)
        local healSub = Magic:Heal(detectedObject, 10) --This subscription will be automatically cancelled when the object leaves the radius, as detectedObject will expire.
    end
end)
```

[obj]: ../../object/
[sub]: ../../subscription/
[hit]: ../../hitdetails/