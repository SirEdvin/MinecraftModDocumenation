# Reality forger

!!! picture inline end
    ![Reality forger](reality_forger.png)

??? info "Supported versions"
    **Forge**: 1.20.x
    **Fabric**: 1.20.x

Do you even want to control the appearance of your home and change it just by pressing a button? Now you can do this; just build your home from flexible reality anchors and use reality forger to control them. You can mimic nearly any block, create dynamic doors, and _forge_ the reality that surrounds you.


## Peripheral methods

| Function                                                 | Returns | Description                                                       |
|----------------------------------------------------------|---------|-------------------------------------------------------------------|
| detectAnchors()                                          | table   | Returns list of all surrounding anchors with relative coordinates |
| forgeRealityPiece(coordinates: [BlockPoses](introduction.md#blockposes), mimic: [Mimic](reality_forger.md#mimic)) | [Result](introduction.md#result)  | Tries to modify the appearance of blocks in the block poses list  |
| forgeReality(mimic: [Mimic](reality_forger.md#mimic))                               | [Result](introduction.md#result)  | Tries to modify appearance of all surrounding blocks              |


### Mimic

Mimic is a type that is used to build block states that should be mimicked. It is a very complex and context-dependent type, so if you experiment with it, you should be prepared to face a lot of Lua exceptions.

Let's start with the basics. If you want to just mimic block, you can use `{block = "minecraft:oak_log"}` to mimic block by ID. There are a number of extra attributes that you can use to modify block logic.
- You can use `playerPassable` attribute to make blocks passable for players. So `{block = "minecraft:oak_log", playerPassable=true}` will create an oak block that the player can just walk through. Take note that blocks will be passable only for players.
- You can use the boolean attributes `lightPassable` and `skyLightPassable` to allow light and skylight to pass or not throw the block.
- You can use the boolean attribute `invisible` to make blocks totally invisible. In addition to `playerPassable` it makes blocks nearly undetectable.

Okay, but what if you want to make a rotated block that you mimic, for example, if the block is `minecraft:oak_stairs`. Parameter `attrs` will allow you to send desired [block state](https://minecraft.fandom.com/wiki/Block_states) values. So, for example, if you want stairs facing east, you can just send `{block="minecraft:oak_stairs", attrs={facing="east}}`. All block state values can be changed via `attrs` attribute, so feel free to use it from time to time.