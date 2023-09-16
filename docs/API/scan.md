# Scan API

!!! picture inline end
    ![Turtle coordinates](turtle_coordinates.png)

Scan API is an interesting one. It allows use to analyze environment around turtle in specific **radius**. However, result always will be orientation-related, direction in which turtle facing will be counted as X axis and direction at right of turtle will be counted as Z axis. This behavior will match Minecraft world axes when turtle facing east.

!!! info
    Most of peripherals, that implements this API will provide only limited subset of scan methods. You can figure out which scan mods are allowed to use via documentation pages or **scanMethods** field from peripheral configuration.

!!! warning
    `radius` should be positive integer


| Function                                         | Returns | Description                                                                                                     |
|--------------------------------------------------|---------|-----------------------------------------------------------------------------------------------------------------|
| scan("item", radius?: number) | table[^1]   | Scan surrounded area for items. |
| scan("block", radius?: number) | table[^2]   | Scan surrounded area for blocks. |
| scan("entity", radius?: number) | table[^3]   | Scan surrounded area for entities. Entities will be prefiltered by specific peripheral conditions |
| scan("player", radius?: number) | table[^4]   | Scan surrounded area for players. |
| scan("xp", radius?: number) | table   | Scan surrounded area for xp orbs. |

[^1]: ??? tip "Item scan output example"
        ```json
        [
            {
                "tags": {},
                "maxCount": 64,
                "displayName": "Rail",
                "y": 0,
                "x": -2,
                "count": 1,
                "z": 0,
                "rawName": "block.minecraft.rail",
                "name": "minecraft:rail",
                "itemGroups": {}
            },
            {
                "tags": {},
                "maxCount": 16,
                "displayName": "Bucket",
                "y": 0,
                "x": -1,
                "count": 1,
                "z": 0,
                "rawName": "item.minecraft.bucket",
                "name": "minecraft:bucket",
                "itemGroups": {}
            }
        ]
        ```

[^2]: ??? tip "Block scan output example"
        ```json
        [
            {
                "y": -1,
                "x": -1,
                "name": "minecraft:grass_block",
                "z": 1,
                "tags": [
                    "..."
                ],
                "displayName": "Grass Block"
            },
            {
                "y": -1,
                "x": 0,
                "name": "minecraft:grass_block",
                "z": 1,
                "tags": [
                    "..."
                ],
                "displayName": "Grass Block"
            },
            {
                "y": 0,
                "x": -1,
                "name": "minecraft:grass",
                "z": 1,
                "tags": [
                    "minecraft:sword_efficient",
                    "minecraft:replaceable_by_trees",
                    "minecraft:enchantment_power_transmitter",
                    "minecraft:mineable/axe",
                    "minecraft:replaceable",
                    "techreborn:mineable/omni_tool"
                ],
                "displayName": "Grass"
            },
            {
                "y": -1,
                "x": -1,
                "name": "minecraft:grass_block",
                "z": 0,
                "tags": [
                    "..."
                ],
                "displayName": "Grass Block"
            },
            {
                "y": -1,
                "x": 0,
                "name": "minecraft:grass_block",
                "z": 0,
                "tags": [
                    "..."
                ],
                "displayName": "Grass Block"
            },
            {
                "y": 0,
                "x": 0,
                "name": "peripheralworks:universal_scanner",
                "z": 0,
                "tags": {},
                "displayName": "Universal scanner"
            },
            {
                "y": -1,
                "x": -1,
                "name": "minecraft:grass_block",
                "z": -1,
                "tags": [
                    "..."
                ],
                "displayName": "Grass Block"
            },
            {
                "y": -1,
                "x": 0,
                "name": "minecraft:dirt",
                "z": -1,
                "tags": [
                    "..."
                ],
                "displayName": "Dirt"
            },
            {
                "y": -1,
                "x": 1,
                "name": "minecraft:grass_block",
                "z": -1,
                "tags": [
                    "..."
                ],
                "displayName": "Grass Block"
            },
            {
                "y": 0,
                "x": -1,
                "name": "minecraft:grass",
                "z": -1,
                "tags": [
                    "minecraft:sword_efficient",
                    "minecraft:replaceable_by_trees",
                    "minecraft:enchantment_power_transmitter",
                    "minecraft:mineable/axe",
                    "minecraft:replaceable",
                    "techreborn:mineable/omni_tool"
                ],
                "displayName": "Grass"
            },
            {
                "y": 0,
                "x": 0,
                "name": "computercraft:computer_advanced",
                "z": -1,
                "tags": [
                    "techreborn:mineable/omni_tool",
                    "minecraft:mineable/pickaxe",
                    "techreborn:mineable/drill",
                    "computercraft:computer"
                ],
                "displayName": "Advanced Computer"
            }
        ]
        ```

[^3]: ??? tip "Entity scan output example"
        ```json
        [
            {
                "type": "Salmon",
                "tags": {},
                "displayName": "Salmon",
                "y": -6,
                "x": -25,
                "health": 3,
                "category": "WATER_AMBIENT",
                "uuid": "86cc9675-55fa-48cc-9fbc-0e4dba5d33bc",
                "name": 15777,
                "z": 7
            },
            {
                "type": "Wandering Trader",
                "tags": {},
                "displayName": "Wandering Trader",
                "y": -1,
                "x": 0,
                "health": 11,
                "category": "CREATURE",
                "uuid": "c3df37a7-4e13-4154-b3cf-ac1491f39a64",
                "name": 6979,
                "z": 2
            },
            {
                "type": "Trader Llama",
                "tags": {},
                "displayName": "Trader Llama",
                "y": 1,
                "x": 0,
                "health": 28,
                "category": "CREATURE",
                "uuid": "17bcda28-fdb8-4f60-b8a0-c28ba9693f9a",
                "name": 6980,
                "z": 0
            },
            {
                "type": "Trader Llama",
                "tags": {},
                "displayName": "Trader Llama",
                "y": 0,
                "x": -1,
                "health": 25,
                "category": "CREATURE",
                "uuid": "78e51c88-ddbd-4442-b228-f2aaa59a5aa2",
                "name": 6981,
                "z": 0
            }
        ]
        ```

[^4]: ??? tip "Player scan output example"
        ```json
        [
            {
                "category": "MISC",
                "type": "Player",
                "foodLevel": 20,
                "saturationLevel": 5,
                "xRot": 35.249980926514,
                "yRot": 161.84989929199,
                "y": 0,
                "displayName": "SirEdvin",
                "experienceLevel": 0,
                "isCreative": true,
                "health": 20,
                "z": -1,
                "x": 2,
                "name": 181,
                "tags": {},
                "uuid": "<some_uuid>"
            }
        ]
        ```