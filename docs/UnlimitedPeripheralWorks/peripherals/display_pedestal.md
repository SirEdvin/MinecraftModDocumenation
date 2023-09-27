# Display pedestal

!!! picture inline end
    ![Dispaly pedestal](display_pedestal.png)

??? info "Supported versions"
    **Forge**: 1.19.4, 1.20.x
    **Fabric**: 1.19.4, 1.20.x

This pedestal can display anything. Like, literally any item in the game. It is such a pity, that you can't take this item, because this is just a visualization. To compensate this disturbing filling of lost opportunities, this pedestal will also fire events when someone click on it with left or right mouse button.

## Peripheral methods

| Function                                         | Returns                          | Description                                                                    |
|--------------------------------------------------|----------------------------------|--------------------------------------------------------------------------------|
| getItem()                                        | table                            | Returns information about current displayed item                               |
| setItem(id: string, name?: string, nbt?: string) | [Result](introduction.md#result) | Tries to set new item to display. NBT should be json string, see example below |
| isLabelRendered()                                | boolean                          | Returns true if label should be renderer, false otherwise                      |
| isItemRendered()                                 | boolean                          | Returns true if item should be renderer, false otherwise                       |
| setLabelRendered(value: boolean)                 | nil                              | Allows to change is label should be rendered to not                            |
| setItemRendered(value: boolean)                  | nil                              | Allows to change is item should be rendered to not                             |

> [!tip]- How in hell does nbt works?
> NBT data passing from ComputerCraft to Minecraft are ... complicated task. So currently, `nbt` are just string that expected to be minecraft NBT data serialized into json. 
> You can try `setItem("minecraft:potion", nil, "{Potion:\"minecraft:long_regeneration\"}")` to understand how it works


## Events

For any computer connected to display pedestal, you will receive a set of events

### pedestal_left_click

When some player clicked on pedestal with left click

#### Values

1. `itemInHand: table` item in player hand

### pedestal_right_click

When some player clicked on pedestal with right click

#### Values

1. `itemInHand: table` item in player hand