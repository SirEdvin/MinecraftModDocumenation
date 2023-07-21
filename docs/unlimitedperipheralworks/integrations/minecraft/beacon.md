# Beacon

!!! picture inline end
    ![Beacon](beacon.png)

If you ever wants to control beacon automatically and change it powers, now you can!

<br />
<br />
<br />

## Beacon configuration

Beacon configuration can be complicated at first, but you need to think about it like regular beacon configuration:

- You select one of primary powers with `power` argument (should be effect id, like `minecraft:haste`, full list you can get via `getPossiblePowers()`)
- Than you need to selected inventory with payment for beacon reconfiguration. By default, this method will take first item in this inventory with `minecraft:beacon_payment_items` tag, but you can specify exact item ID (like `minecraft:iron_ingot`) via optional `item` parameter.
- If your beacon has 4 level, by default selected effect will get second level. If you want to select regeneration instead, pass `regeneration` as true.

??? warning "Compitablity note"
    - 1.18 and 1.19.2 versions of UnlimitedPeripheralWorks uses `effect.minecraft.haste` as ID for effects

## Peripheral methods

| Function                                                                      | Returns | Description                                                                              |
|-------------------------------------------------------------------------------|---------|------------------------------------------------------------------------------------------|
| getLevel()                                                                    | number  | Returns current beacon level, can be from 1 to 4                                         |
| getPossiblePowers()                                                           | table   | Returns list of possible primary effects, that can selected                              |
| getPowers()                                                                   | table   | Returns list of currently active effects                                                 |
| configure(power: string, from: string, itemQuery?: [ItemQuery](introduction.md#itemquery), regeneration?: boolean) | [Result](introduction.md#result)  | Tries to configure beacon with selected power, consuming single item from `from` storage |

!!! warning
    ItemQuery scope in any case will be reduces to items with tag `minecraft:beacon_payment_items`
