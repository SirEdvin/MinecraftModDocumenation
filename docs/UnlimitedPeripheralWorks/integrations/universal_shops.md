# Unversal shops

!!! picture inline end
    ![Universal shops](universal_shop.png)

??? info "Supported versions"
    **Fabric**: 1.20.x

[Unversal shops](https://modrinth.com/mod/universal-shops) is a Fabric (and Quilt compatible) trade shop mod designed to be flexible and usable in many types of servers. It works purely server side (still works on singleplayer), so it can work on your vanilla client compatible or modpack based servers. It includes craftable, Trade Shop block for players and Admin Trade Shop for admins/map makers. Integration allow you to fully configure your shop and also extract or insert items into this.

## Supported APIs

- [inventory](https://tweaked.cc/generic_peripheral/inventory.html) API

## Peripheral methods

| Function                                  | Returns | Description                                                                                                          |
|-------------------------------------------|---------|----------------------------------------------------------------------------------------------------------------------|
| getHologramMode()                         | string  | Returns current hologram mode                                                                                        |
| setHologramMode(value: string)            | nil     | Tries to set hologram mode, possible options are full, icon and disabled                                             |
| getPrice()                                | table   | Returns information about current price mode with configuration if present                                           |
| getStock()                                | table   | Returns information about current stock mode with configuration if present                                           |
| setPrice(mode: string, stack?: [ItemStack](introduction.md#itemstack)) | [Result](introduction.md#result)  | Tries to set price mode. It can be free or single_item. For single_item it is required to pass stack argument        |
| setStock(mode: string, stack?: [ItemStack](introduction.md#itemstack)) | [Result](introduction.md#result)  | Tries to set sto mode. It can be selected_item or single_item. For single_item it is required to pass stack argument |
