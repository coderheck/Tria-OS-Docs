# Tria.OS Map Library

This DOES include deprecated items.

## Methods
### MapLib:Alert(message: `string`, color: `Color3?`, length: `number?`): `nil`

Example:
```lua
MapLib:Alert("This is an Alert!", Color3.fromRGB(255, 255, 255), 10)
```
This function can be used to send a message to everyone, they can be customized by color and duration.

-----------------------------------------------------

### MapLib:ChangeMusic(musicId: `string|number`, volume: `number?`, startTick: `number?`): `nil`

Example:
```lua
MapLib:ChangeMusic(8166551934, 0.5, 5) --changes the background music to 8166551934 and plays it with the volume of 0.5 and the start time (in seconds) of 5.
```
This function can be used to change the current music playing in maps, this also replicates to spectators.

-----------------------------------------------------

### MapLib:GetButtonEvent(buttonId: `number`): `Event`

Example:
```lua
MapLib:GetButtonEvent(5):Connect(function(player) -- player value here is the player that pressed the button.
    MapLib:Alert("Button 5 was pressed!", Color3.fromRGB(255, 255, 255), 4)
end)
```
This function is the equivalent of `Lib.btnFuncs[5] = function() end` in Flood Escape 2. It can be used to run functions once a button has been pressed.

-----------------------------------------------------

### MapLib:SetLiquidType(liquid: `BasePart`, liquidType: `string`): `nil`
Example:
```lua
MapLib:SetLiquidType(MapLib.map._Liquid1, "lava") -- changes Liquid1 to lava.
```
This function can be used to change the state of a liquid. There are 3 states you can choose from excluding custom states, these are "water", "acid" and "lava".

-----------------------------------------------------

### MapLib:Move(moveable: `PVInstance`, movement: `Vector3`, duration: `number?`)
Example:
```lua
local maplib = game.GetMapLib:Invoke()()
local map = maplib.map
MapLib:Move(map.MovingPart, Vector3.new(12, 0, 0), 3)
```
Used to move `PVInstances` (ex. `BasePart`, `Model`)

-----------------------------------------------------

### MapLib:MoveRelative(moveable: `PVInstance`, movement: Vector3, duration: number?)
```lua
local maplib = game.GetMapLib:Invoke()()
local map = maplib.map
MapLib:Move(map.MovingPart, Vector3.new(12, 0, 0), 3)
```
Used to move `PVInstances` locally.

-----------------------------------------------------

### MapLib:Survive(player: `string`)
Example:
```lua
local maplib = game.GetMapLib:Invoke()()
local player = game.Players:GetPlayerFromCharacter(other.Parent)
if (player ~= nil) then
    MapLib:Survive(player)
end
```
This function can be used to make the player survive the match without touching ExitRegion.

-----------------------------------------------------

### MapLib:MovePart(part: `BasePart`, movement: `Vector3`, duration: `number?`): `nil`
old but still usable, merged into `MapLib:Move()`

-----------------------------------------------------

### MapLib:MovePartLocal(part: `BasePart`, movement: `Vector3`, duration: `number?`): `nil`
old but still usable, merged into `MapLib:MoveRelative()`

-----------------------------------------------------

### MapLib.MoveModel(moveable: `Model`, movement: `Vector3`, duration: `number?`)
old but still usable, merged into `MapLib:Move()`

-----------------------------------------------------

### MapLib.MoveModelLocal() - acts as MapLib.MoveRelative(moveable: `Model`, movement: `Vector3`, duration: `number?`)
old but still usable, merged into `MapLib:MoveRelative()`



### MapLib:GetFeature(featureName: `string`)
`:GetFeature()` is used to get any features listed in FeatureLib.md.
