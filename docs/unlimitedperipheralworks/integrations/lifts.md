# Lifts

[Lifts](https://www.curseforge.com/minecraft/mc-mods/lifts) a technology mod that adds various lifts for better vertical traversal inside your world.

This integration allows you to control lift and moves it via CC computers. Any lift controller will provide such capabilities to you

??? info "Supported versions"
    **Fabric**: Only 1.18

## Peripheral methods

| Function                    | Returns        | Description                                                       |
|-----------------------------|----------------|-------------------------------------------------------------------|
| floors()                    | table          | Returns list of floors with information about related controllers |
| getCurrentFloor()           | [Result](introduction.md#result)[number] | Get current floor index                                           |
| getFloorName(floor: number) | string         | Get floor name, how it will be displayed on lift controller hud   |
| changeFloor(floor: number)  | [Result](introduction.md#result) | Tries to send lift to selected floor                              |