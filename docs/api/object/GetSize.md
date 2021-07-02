# Object:GetSize
The size of an object is based on its diagonal width. The size of a default character is considered to be the average size of an object, and will return a value of 1. All other sizes are scaled accordingly (i.e. an object with twice the diagonal width of a character model will have a size of 2). The exact calculation for size is as follows:
```lua
local characterDiagonalWidth = Vector3.new(4, 5, 1).Magnitude
return object:GetDimensions().Magnitude/characterDiagonalWidth
```