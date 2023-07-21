# Mercantile automata

!!! picture inline end
    ![Mercantile automata](mercantile_automata.png)

Automata that harness power of wandering trader, allows you to trade with other (more lucky) wandering traders and villagers.

## Obtaining

Feed wandering trader to forged automata core with [soul scrapper](soul_scrapper.md) to obtain it.

## Supported APIs

- [Configuration API](configuration.md)
- [Fuel API](fuel.md)
- [Operation API](operation.md)
- [Look API](look.md)
- [Suck API](suck.md)
- [Experience API](experience.md)
- [Scan API](scan.md): only for items and merchants

## Extra methods

| Function                                                                     | Returns                                  | Description                                                                                                                                                                                                                                                                                                  |
| ---------------------------------------------------------------------------- | ---------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| trade(hint?: int, direction?: [Direction](introduction.md#direction)) | [Result](introduction.md#result)[number] | Performs a trade operation, taking as trading inputs item in selected slot and item next to it (if selected slot isn't last). Returns amount of purcased items. If several trades available with this combination of items, hint is required. Order of traders in sync with offers list from `look` function |
| restock(direction?: [Direction](introduction.md#direction))           | [Result](introduction.md#result)         | Tries to restock offers. Will work only for villagers, available for Starbound core version                                                                                                                                                                                                                  |

## Notes

> [!tip]- XP notes
> XP from trading operations will not be gather automatically and should be collected via `collectXP` function

> [!tip]- How I can get information about merchant trades?
> Just use `look("entity")` function! Output of merchant entity will be enriched with `offers`. Sometimes, this list can contains `nil` elements, which means, that this offers are out of stock.
> ```json
> {
>    "type":"Wandering Trader",
>    "name":"Wandering Trader",
>    "category":"CREATURE",
>    "id":448,
>    "tags":{
>       
>    },
>    "uuid":"1816f543-4fc5-47c6-bf37-8d27451df116",
>    "offers":[
>       {
>          "inputs":[
>             {
>                "name":"Emerald",
>                "maxStackSize":64,
>                "tags":[
>                   "c:emeralds",
>                   "minecraft:beacon_payment_items"
>                ],
>                "technicalName":"minecraft:emerald",
>                "count":1
>             }
>          ],
>          "outputs":[
>             {
>                "name":"White Dye",
>                "maxStackSize":64,
>                "tags":[
>                   "c:dyes",
>                   "c:white_dyes"
>                ],
>                "technicalName":"minecraft:white_dye",
>                "count":3
>             }
>          ]
>       },
>       {
>          "inputs":[
>             {
>                "name":"Emerald",
>                "maxStackSize":64,
>                "tags":[
>                   "c:emeralds",
>                   "minecraft:beacon_payment_items"
>                ],
>                "technicalName":"minecraft:emerald",
>                "count":5
>             }
>          ],
>          "outputs":[
>             {
>                "name":"Nautilus Shell",
>                "maxStackSize":64,
>                "tags":{
>                   
>                },
>                "technicalName":"minecraft:nautilus_shell",
>                "count":1
>             }
>          ]
>       },
>       {
>          "inputs":[
>             {
>                "name":"Emerald",
>                "maxStackSize":64,
>                "tags":[
>                   "c:emeralds",
>                   "minecraft:beacon_payment_items"
>                ],
>                "technicalName":"minecraft:emerald",
>                "count":1
>             }
>          ],
>          "outputs":[
>             {
>                "name":"Wheat Seeds",
>                "maxStackSize":64,
>                "tags":{
>                   
>                },
>                "technicalName":"minecraft:wheat_seeds",
>                "count":1
>             }
>          ]
>       },
>       {
>          "inputs":[
>             {
>                "name":"Emerald",
>                "maxStackSize":64,
>                "tags":[
>                   "c:emeralds",
>                   "minecraft:beacon_payment_items"
>                ],
>                "technicalName":"minecraft:emerald",
>                "count":1
>             }
>          ],
>          "outputs":[
>             {
>                "name":"Purple Dye",
>                "maxStackSize":64,
>                "tags":[
>                   "c:dyes",
>                   "c:purple_dyes"
>                ],
>                "technicalName":"minecraft:purple_dye",
>                "count":3
>             }
>          ]
>       },
>       {
>          "inputs":[
>             {
>                "name":"Emerald",
>                "maxStackSize":64,
>                "tags":[
>                   "c:emeralds",
>                   "minecraft:beacon_payment_items"
>                ],
>                "technicalName":"minecraft:emerald",
>                "count":1
>             }
>          ],
>          "outputs":[
>             {
>                "name":"Light Blue Dye",
>                "maxStackSize":64,
>                "tags":[
>                   "c:light_blue_dyes",
>                   "c:dyes"
>                ],
>                "technicalName":"minecraft:light_blue_dye",
>                "count":3
>             }
>          ]
>       },
>       {
>          "inputs":[
>             {
>                "name":"Emerald",
>                "maxStackSize":64,
>                "tags":[
>                   "c:emeralds",
>                   "minecraft:beacon_payment_items"
>                ],
>                "technicalName":"minecraft:emerald",
>                "count":3
>             }
>          ],
>          "outputs":[
>             {
>                "name":"Podzol",
>                "maxStackSize":64,
>                "tags":[
>                   "minecraft:dirt"
>                ],
>                "technicalName":"minecraft:podzol",
>                "count":3
>             }
>          ]
>       }
>    ]
> }
> ```