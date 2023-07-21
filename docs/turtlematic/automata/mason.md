# Mason automata

!!! picture inline end
    ![Mason automata](mason_automata.png)

Automata that harness power of mason villager, allows you to modify appearance of different blocks in world and inventory.

Mason automata also has mod support:

- [Chipped](https://www.curseforge.com/minecraft/mc-mods/chipped)

## Obtaining

Feed mason villager to forged automata core with [soul scrapper](soul_scrapper.md) to obtain it.

## Supported APIs

- [Configuration API](configuration.md)
- [Fuel API](fuel.md)
- [Operation API](operation.md)
- [Look API](look.md)
- [Suck API](suck.md)
- [Experience API](experience.md)

## Extra methods

| Function                                                                            | Returns                          | Description                                                                                                                                                                              |
| ----------------------------------------------------------------------------------- | -------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| getAlternatives("inventory")                                                        | table                            | Returns list of possible alternatives for item in selected slot                                                                                                                          |
| getAlternatives("block", direction?: [Direction](introduction.md#direction))        | table                            | Returns list of possible alternatives for block in world                                                                                                                                 |
| chisel("inventory", target: string, limit?: number)                                 | [Result](introduction.md#result) | Tries to chisel item in selected slot in inventory up to limit amount. Result will be put into inventory, extra items will be dropped in world                                           |
| chisel("block", target: string, direction?: [Direction](introduction.md#direction)) | [Result](introduction.md#result) | Tries to chisel block in world. If this is possible, block will be transformed in-place, if this is not possible result will be put into inventory, extra items will be dropped in world |
| rotate(rotation: Rotation, direction?: [Direction](introduction.md#direction))      | [Result](introduction.md#result) | Tries to rotate block in-place                                                                                                                                                           |
| turnOver(direction?: [Direction](introduction.md#direction))                        | [Result](introduction.md#result) | Tries to turn over block in-place                                                                                                                                                        |
| getPossibleShapes(direction?: [Direction](introduction.md#direction))               | table                            | Returns list of possible shapes for block                                                                                                                                                |
| changeShape(shape: string, direction?: [Direction](introduction.md#direction))      | [Result](introduction.md#result) | Tries to transform block to passed shape                                                                                                                                                 |

## Notes

> [!tip]- Extra information about blocks
> To help you understand position of block, mason automata will return extra information when using [Look API](look.md)
> 
> ```javascript
> {
>     "name": "Mossy Stone Brick Stairs",
>     "tags": [
>         "minecraft:stairs",
>         "minecraft:mineable/pickaxe"
>     ],
>     "properties": {
>         "facing": "north",
>         "half": "bottom",
>         "shape": "straight",
>         "watterlogged": "false"
>     }
> }
> ```
