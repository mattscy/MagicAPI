# Object:GetScale
The scale of an object is based on its diagonal width. The scale of a default character is considered to be the average scale of an object, and will return a value of 1. All other scales are adjusted accordingly (i.e. an object with twice the diagonal width of a character model will have a scale of 2). The exact calculation for scale is as follows:
```lua
local characterDiagonalWidth = Vector3.new(4, 5, 1).Magnitude
local objectDiagonalWidth = object:GetDimensions().Magnitude
return objectDiagonalWidth/characterDiagonalWidth
```