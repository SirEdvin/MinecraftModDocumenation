# Brewing automata

!!! picture inline end
    ![Brewing automata](brewing_automata.png)

Automata that harness power of cleric villager, allows you to perform brew potions, throw it and curing villagers

## Obtaining

Feed cleric villager to forged automata core with [soul scrapper](soul_scrapper.md) to obtain it.

## Supported APIs

- [Configuration API](configuration.md)
- [Fuel API](fuel.md)
- [Operation API](operation.md)
- [Look API](look.md)
- [Suck API](suck.md)
- [Experience API](experience.md)
- [Scan API](scan.md): only for items and zombie villagers
- [Interaction API](interaction.md): only for blocks and zombie villagers

## Extra methods

=== "1.19.4"

    | Function                                          | Returns | Description                                                                                                     |
    |---------------------------------------------------|---------|-----------------------------------------------------------------------------------------------------------------|
    | brew()                                            | [Result](introduction.md#result)  | Performs brew operations, applying item in selected slot as brewing component to all potions in inventory.      |
    | throwPotion(power: number, angle: number) | [Result](introduction.md#result)  | Throws potion in selected slot with provided power and angle (in degrees) |


=== "1.18/1.19.2"

    | Function                                          | Returns | Description                                                                                                     |
    |---------------------------------------------------|---------|-----------------------------------------------------------------------------------------------------------------|
    | brew()                                            | [Result](introduction.md#result)  | Performs brew operations, applying item in selected slot as brewing component to all potions in inventory.      |
    | throwPotion(power?: number, uncertainty?: number) | [Result](introduction.md#result)  | Throws potion in selected slot with provided power (controls max distance) and uncertainty (controls deviation) |


## Notes

> [!tip]- XP notes
> Brewing operations often provides some XP that will be stored in turtle

> [!tip]- Extra information about zombie villagers
> To help you understand power of your potions, you will receive extra information about entities with [Look API](look.md) and [Scan API](scan.md)
> 
> ```javascript
> {
>     "type": "Cow",
>     "name": "Cow",
>     "category": "CREATURE",
>     "id": 1269,
>     "tags": {},
>     "uuid": "0737fd25-a1b6-4a1a-9cdd-3081e0155bb6",
>     "effects": [
>         {
>             "amplifier": 0,
>             "duration": 1474,
>             "isAmbient": false,
>             "name": "Regeneration",
>             "technicalName": "minecraft:regeneration"
>         }
>     ]
> }
> ```

> [!tip]- How do I supposed to get water bottles?
> You can `use` glass bottles on water sources
