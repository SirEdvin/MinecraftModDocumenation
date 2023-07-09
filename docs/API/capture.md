# Capture API

Capture API allows moving block or entities with storing it internal data! So finally, you can move specific spawners and chests!

Take a note, that released entity or block will be placed at front of turtle. Also, block can be placed only on empty space

!!! warning
    Before 1.0.0, due to ComputerCraft limitations stored entity will be lost if you unequip turtle upgrade.

| Function                                              | Returns | Description                                                    |
|-------------------------------------------------------|---------|----------------------------------------------------------------|
| capture(mode: [InteractionMode](introduction.md#interaction-mode), direction?: [Direction](introduction.md#direction)) | [Result](introduction.md#result)  | Tries to capture object: entity or block                       |
| release()                                             | [Result](introduction.md#result)  | Tiers to release object: create entity or place block          |
| getCaptured()                                         | table   | Returns information about captured entity (including NBT data) |


??? tip "My modpack have blocks or entities, that crash game when captured, what I can do?"
    Add tag `turtlematic:capture_blacklist` to those blocks or entities.
