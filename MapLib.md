# Tria.OS Map Library

This DOES include deprecated items. (idk which one)

## Methods

### MapLib:Alert(message: `string`, color: [`Color3`](https://create.roblox.com/docs/reference/engine/datatypes/Color3), length: [`number`](https://create.roblox.com/docs/scripting/luau/numbers): `nil`

Example:

```lua
MapLib:Alert("This is an Alert!", Color3.fromRGB(255, 255, 255), 10)
```

This function can be used to send a message to everyone. The message can be customized by color and duration.

-----------------------------------------------------

### MapLib:ChangeMusic(musicId: `string|number`, volume: [`number`](https://create.roblox.com/docs/scripting/luau/numbers), startTick: [`number`](https://create.roblox.com/docs/scripting/luau/numbers): `nil`

Example:

```lua
MapLib:ChangeMusic(8166551934, 0.5, 5) --changes the background music to 8166551934 and plays it with the volume of 0.5 and the start time (in seconds) of 5.
```

This function can be used to change the current music playing in maps, this also replicates to spectators.

-----------------------------------------------------

### MapLib:GetButtonEvent(buttonId: [`number`](https://create.roblox.com/docs/scripting/luau/numbers)): [`RBXScriptSignal`](https://create.roblox.com/docs/reference/engine/datatypes/RBXScriptSignal)

Example:

```lua
MapLib:GetButtonEvent(5):Connect(function(player) -- player value here is the player that pressed the button.
    MapLib:Alert("Button 5 was pressed!", Color3.fromRGB(255, 255, 255), 4)
end)
```

This function is the equivalent of `Lib.btnFuncs[5] = function() end` in Flood Escape 2. It can be used to run functions once a button has been pressed.

-----------------------------------------------------

### MapLib:SetLiquidType(liquid: [`BasePart`](https://create.roblox.com/docs/reference/engine/classes/BasePart), liquidType: `string`): `nil`

Example:

```lua
MapLib:SetLiquidType(MapLib.map._Liquid1, "lava") -- changes Liquid1's liquid type to lava.
```

This function can be used to change the state of a liquid. There are 3 states you can choose from excluding custom states, these are "water", "acid" and "lava".

-----------------------------------------------------

### MapLib:Move(moveable: [`PVInstance`](https://create.roblox.com/docs/reference/engine/classes/PVInstance), movement: [`Vector3`](https://create.roblox.com/docs/reference/engine/datatypes/Vector3), duration: [`number?`](https://create.roblox.com/docs/scripting/luau/numbers)): `nil`

Example:

```lua
local maplib = game.GetMapLib:Invoke()()
local map = maplib.map
MapLib:Move(map.MovingPart, Vector3.new(12, 0, 0), 3)
```

Used to move [`PVInstances`](https://create.roblox.com/docs/reference/engine/classes/PVInstance), replicates to all clients (visible to all players).

-----------------------------------------------------

### MapLib:MoveRelative(moveable: [`PVInstance`](https://create.roblox.com/docs/reference/engine/classes/PVInstance), movement: [`Vector3`](https://create.roblox.com/docs/reference/engine/datatypes/Vector3), duration: [`number?`](https://create.roblox.com/docs/scripting/luau/numbers)): `nil`

```lua
local maplib = game.GetMapLib:Invoke()()
local map = maplib.map
MapLib:Move(map.MovingPart, Vector3.new(12, 0, 0), 3)
```

Used to move [`PVInstances`](https://create.roblox.com/docs/reference/engine/classes/PVInstance), does not replicate to all clients (only visible to the player that the script is running for).

-----------------------------------------------------

### MapLib:Survive(player: `string`): `nil`

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

### MapLib:MovePart(part: [`BasePart`](https://create.roblox.com/docs/reference/engine/classes/BasePart), movement: [`Vector3`](https://create.roblox.com/docs/reference/engine/datatypes/Vector3), duration: [`number`](https://create.roblox.com/docs/scripting/luau/numbers)): `nil`

old but still usable, merged into `MapLib:Move()`

-----------------------------------------------------

### MapLib:MovePartLocal(part: [`BasePart`](https://create.roblox.com/docs/reference/engine/classes/BasePart), movement: [`Vector3`](https://create.roblox.com/docs/reference/engine/datatypes/Vector3), duration: [`number`](https://create.roblox.com/docs/scripting/luau/numbers)): `nil`

old but still usable, merged into `MapLib:MoveRelative()`

-----------------------------------------------------

### MapLib.MoveModel(moveable: [`Model`](https://create.roblox.com/docs/reference/engine/classes/Model), movement: [`Vector3`](https://create.roblox.com/docs/reference/engine/datatypes/Vector3), duration: [`number`](https://create.roblox.com/docs/scripting/luau/numbers)): `nil`

old but still usable, merged into `MapLib:Move()`

-----------------------------------------------------

### MapLib.MoveModelLocal(moveable: [`Model`](https://create.roblox.com/docs/reference/engine/classes/Model), [`Vector3`](https://create.roblox.com/docs/reference/engine/datatypes/Vector3), duration: [`number`](https://create.roblox.com/docs/scripting/luau/numbers)): `nil`

old but still usable, merged into `MapLib:MoveRelative()`

-----------------------------------------------------

### MapLib:GetFeature(featureName: `string`)

`:GetFeature()` is used to get any features listed in [the features list](FeatureLib.md)

-----------------------------------------------------

### MapLib:GetPlayers(): [`Tuple`](https://create.roblox.com/docs/scripting/luau/tuples)

`:GetPlayers()` returns a [`Tuple`](https://create.roblox.com/docs/scripting/luau/tuples) containing players currently in a map.
