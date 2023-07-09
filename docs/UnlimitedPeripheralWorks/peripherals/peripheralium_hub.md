# Peripheralium hub

!!! picture inline end
    ![Peripheralium hub](peripheralium_hub_turtle.png)

??? info "Supported versions"
    **Forge**: 1.19.4, 1.20.x
    **Fabric**: 1.19.4, 1.20.x

!!! warning
    Prior to 1.0.0 version, due to ComputerCraft limitations, all equipped upgrades will be deleted if you brake turtle or remove peripheralium hub without unequipping upgrades

Turtle limited to two upgrade slots and pocket computers to one. With all this nasty new add-ons to CC:T it sometimes becomes a pain to select what upgrade you want to install. But with this hub, you can install all of them! 

Nah, unfortunately, only 3 for base version and 7 for netherite one, but this is still something. And of course, both turtles and pocket computers are supported!

## Supported APIs

- [Configuration API](configuration.md)
- `peripheral_hub` api for CC:T, so this upgrade actually work as modem and provide access to peripherals inside it.

## Peripheral methods

| Function                | Returns                          | Description                                                                                             |
|-------------------------|----------------------------------|---------------------------------------------------------------------------------------------------------|
| isUpgrade(slot: number) | boolean                          | Returns true if item in slot can be used as upgrade, false otherwise                                    |
| equip(slot: number)     | [Result](introduction.md#result) | Tries to equip item in slot as an upgrade.                                                              |
| unequip(id: string)     | [Result](introduction.md#result) | Tries to unequip upgrade to inventory. If inventory is full, an upgrade item will be dropped on the ground |
| getUpgrades()           | table                            | Returns ids of all equipped upgrades                                                                    |
