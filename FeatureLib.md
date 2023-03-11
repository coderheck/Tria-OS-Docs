# Tria.OS Features Library

## NOTE: DO NOT USE ANY FEATURES LABELED AS "DEPRECATED".

## Lighting (DEPRECATED)
This section lists all features releated to Lighting.

### LightingFeature:SetLighting(newLighting: `{ [string]: any }`)
Example: 
```lua
MapLib:GetFeature("Lighting"):SetLighting({
        FogEnd = 100,
        FogStart = 1,
        FogColor = Color3.new(1, 0, 0),
        Ambient = Color3.new(1, 1, 0),
	OutdoorAmbient = Color3.new(1, 0, 1),
})
```
Used to set the lighting of maps, such as the Ambient and FogColor.

### LightingFeature:EaseLighting(newLighting: `{ [string]: any }`, tweenInfo: `TweenInfo`)
Example:
```lua
MapLib:GetFeature("Lighting"):EaseLighting({
	FogEnd = 100,
	FogStart = 1,
	FogColor = Color3.new(0, 1, 1),
},TweenInfo.new(4, Enum.EasingStyle.Sine, Enum.EasingDirection.Out))
```
Tweens the lighting to the values set in the function. They can be customized by lighting and the way the lighting tweens (by using `TweenInfo`).

## Players (DEPRECATED)
This section lists all features releated to Lighting.

### PlayersFeature:GetPlayers(): `[Player]`
Example:
```lua
MapLib:GetFeature("Players"):GetPlayers()
```
old/deprecated, use MapLib:GetPlayers()

## Miscellaneous

### MapLib:AllowSliding(slideState: `boolean`): `nil`

Example:
```lua
MapLib:AllowSliding(true)
```
This function can be used to change sliding state in maps. `true` enables sliding and `false` disables sliding.
