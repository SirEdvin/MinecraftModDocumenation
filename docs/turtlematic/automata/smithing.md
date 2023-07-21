# Smithing automata

!!! picture inline end
    ![Smithing automata](smithing_automata.png)

Automata that harness power of toolsmithing villager, allows you to perform smithing operation and smelt items.

## Obtaining

Feed toolsmithing villager to forged automata core with [soul scrapper](soul_scrapper.md) to obtain it.

## Supported APIs

- [Configuration API](configuration.md)
- [Fuel API](fuel.md)
- [Operation API](operation.md)
- [Look API](look.md)
- [Suck API](suck.md)
- [Experience API](experience.md)

## Extra methods

| Function                             | Returns | Description                                                                                                                                                                                |
|--------------------------------------|---------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| smith()                              | [Result](introduction.md#result)  | Perform smithing operation, using selected slot and two next slots                                                                                                                   |
| smelt("inventory", limit?: number)   | [Result](introduction.md#result)  | Tries to smelt item in selected slot in inventory up to limit amount. Result will be put into inventory, extra items will be dropped in world                                              |
| smelt("block", direction?: [Direction](introduction.md#direction) | [Result](introduction.md#result)  | Tries to smelt block in world. If this is possible, block will be transformed in-place, if this is not possible result will be put into inventory, extra items will be dropped in world | |

## Notes

> [!tip]- Smith operation
> Before 1.20, smith operation uses only selected slot and next one.

> [!tip]- XP notes
> All XP for smelting operations will be stored inside turtle
