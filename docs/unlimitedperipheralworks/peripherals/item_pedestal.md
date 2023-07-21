# Item pedestal

!!! picture inline end
    ![Item pedestal](item_pedestal.png)

??? info "Supported versions"
    **Forge**: 1.19.4, 1.20.x
    **Fabric**: 1.19.4, 1.20.x

Who doesn't want a nice, cute little pedestal, that can be used to store and display items? Well, now you have one. But this peripheral also allows you to inspect item NBT data, when item is placed on this pedestal. Place items with right click, and retrieve items with left click with empty hand.

## Supported APIs

- [inventory](https://tweaked.cc/generic_peripheral/inventory.html) API from CC:T. With only difference, that `getItemDetail` returns also `rawNBT` table value.