# Map pedestal

!!! picture inline end
    ![Map pedestal](map_pedestal.png)

??? info "Supported versions"
    **Forge**: 1.19.4, 1.20.x
    **Fabric**: 1.19.4, 1.20.x

One cute pedestal is nice, but two cute pedestals is much better. In additionally to being cute, this pedestal allows you to get information from minecraft maps and even update them time to time. And because of this, only maps can be placed on this pedestal. Place map with right click, and retrieve map back with left click with empty hand.

## Supported APIs

- [inventory](https://tweaked.cc/generic_peripheral/inventory.html) API from CC:T.  With only difference, that `getItemDetail` returns also `rawNBT` table value.
- [Configuration API](configuration.md)
- [Operation API](operation.md)

## Peripheral methods


| Function     | Returns                                 | Description                                                                            |
|--------------|-----------------------------------------|----------------------------------------------------------------------------------------|
| getData()    | [Result](introduction.md#result)[table] | Returns table with extracted information from map, including colors, scale and banners |
| updateData() | [Result](introduction.md#result)        | Tries to update information on map                                                     |