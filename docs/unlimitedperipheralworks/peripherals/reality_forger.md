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
| forgeRealityPieces(coordinates: list[[BlockPos](introduction.md#blockpos)], blockState: [BlockState](introduction.md#blockstate), options?: [Options](reality_forger.md#options)) | [Result](introduction.md#result)  | Tries to modify the appearance of blocks in the block poses list  |
| batchForgeRealityPieces(instructions: [Instructions](reality_forger.md#instructions))) | [Result](introduction.md#result)  | Tries to modify the appearance of blocks following instructions in one tick  |
| forgeReality(mimic: blockState: [BlockState](introduction.md#blockstate), options?: [Options](reality_forger.md#options))                               | [Result](introduction.md#result)  | Tries to modify appearance of all surrounding blocks              |


??? info "Compitability info"
    In previous versions (prior to 1.1.0) it was possible to pass [options](reality_forger.md#options) flags inside [blockstate](introduction.md#blockstate) argument.

    It is still work for backward compitability, but will be removed in next major minecraft update

### Options

Options is just a table with "key" and boolean value `false` or `true`.

- You can use `playerPassable` attribute to make blocks passable for players. So `{playerPassable=true}` will create an oak block that the player can just walk through. Take note that blocks will be passable only for players.
- You can use the boolean attributes `lightPassable` and `skyLightPassable` to allow light and skylight to pass or not throw the block.
- You can use the boolean attribute `invisible` to make blocks totally invisible. In addition to `playerPassable` it makes blocks nearly undetectable.


### Instructions

Type descriptions: list[list[[BlockPos](introduction.md#blockpos)], [BlockState](introduction.md#blockstate), [Options](reality_forger.md#options)]]

Because `batchForgeRealityPieces` is method designed to execute multiple `forgeRealityPieces` in one tick, `batchForgeRealityPieces` just accepts list of arguments for this method.

So, you expected to pass something like:

```lua
p.batchForgeRealityPieces({
    {{{x=0, y=0, z=1}, {x=1, y=1, z=1}}, {block="minecraft:oak_log"}},
    {{{x=1, y=0, z=1}}, {block="minecraft:birch_log"}, {playerPassable = true}}
})
```