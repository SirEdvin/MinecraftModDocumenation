# Enchanting automata

!!! picture inline end
    ![Enchanting automata](enchanting_automata.png)

Automata that harness power of librarian villager, allows you to works with enchantments.

## Obtaining

Feed librarian villager to forged automata core with [soul scrapper](soul_scrapper.md) to obtain it.

## Supported APIs

- [Configuration API](configuration.md)
- [Fuel API](fuel.md)
- [Operation API](operation.md)
- [Suck API](suck.md)
- [Experience API](experience.md)

## Extra methods

| Function                           | Returns | Description                                                                                                                                                                                                                                    |
|------------------------------------|---------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| getEnchantmentPower()              | number  | Returns current enchantment power around turtle                                                                                                                                                                                                |
| getPossibleEnchantments()          | table   | Returns list of possible enchantment with current enchantment power level for item in selected slot. It will always return 3 suggestions like default enchanting table. Also it always shows only ONE enchantment even if more will be applied |
| refreshEnchantments()              | nil     | Refresh enchantments in list of possible enchantments. This is an only way to get different enchantments without performing enchantments                                                                                                          |
| enchant(selected: number)          | Result  | Tries to perform enchantment on item with selected enchantment from list of possible enchatments. Selected should be 1, 2 or 3. Consumes XP from XP storage as for usual enchantment                                                           |
| extractEnchantment(target: number) | Result  | Tries to extract enchantments from item in selected slot to item in target slot. An item in target slot should contain only 1 book. There is a small chance that one enchantment will be lost in the process                                          |

## Notes

> [!tip]- Enchantment power gathering
> To perform enchantment you need to make sure, that you have enough enchantment power. Any head or bookshelf around turtle (radius of influence is 2 blocks) will give 2 extra points of enchantment power. Take a note, that turtles in the same radius will give two extra enchantment power points per enchanting book in their inventory.

> [!tip]- What gives enchantment power
> By default: bookshelf, heads, candle and candle cake. You can control this via `turtlematic:enchantment_power_provider` tag