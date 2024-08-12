# Entity link

!!! picture inline end
    ![Entity link](entity_link.png)

??? info "Supported versions"
    **Forge**: 1.20.x
    **Fabric**: 1.20.x


ComputerCraft is a powerful tool that allows you to manipulate different blocks and modify them.
Hey, but what about entities, like minecart or even living creatures like horses with chests? Why they should be left behind? 

Not anymore. With the help of an entity link and [entity card](entity_card.md), you can connect your computer to supported entities! Just insert [entity card](entity_card.md) into it with right click.

If you want to remove card from link, just right click on it with empty hand.

List of supported entities:

- Minecarts with chest or with furnace would additionally provide [inventory](https://tweaked.cc/generic_peripheral/inventory.html) API to this minecart.
- Horses, donkeys and llamas with chests would additionally provide [inventory](https://tweaked.cc/generic_peripheral/inventory.html) API.
- Demons from [Occultism](https://www.curseforge.com/minecraft/mc-mods/occultism) if they have inventory would additionally provide [inventory](https://tweaked.cc/generic_peripheral/inventory.html) API.

## Peripheral functions

| Function        | Returns      | Description                                                                       |
|-----------------|--------------|-----------------------------------------------------------------------------------|
| isEntityFound() | bool         | Returns true if entity connected, false if not                                    |
| inspect()       | table or nil | Returns table description of entity if it is attached, nil if entity is not found |
