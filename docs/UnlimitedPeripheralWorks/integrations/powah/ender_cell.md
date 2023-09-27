# Ender cell

!!! picture inline end
    ![Ender cell](ender_cell_nitro.png)

??? info "Supported versions"
    **Fabric**: 1.20.x
    **Forge**: 1.20.x

Additional integration with the ender cell allows you to not only see the amount of stored energy but also provide information about the current active channel in addition to the way to switch this channel.

## Supported API

- [energy_storage](https://tweaked.cc/generic_peripheral/energy_storage.html) API
- [Redstone API](powah_redstone_api.md)

## Peripheral methods

| Function                    | Returns | Description                 |
|-----------------------------|---------|-----------------------------|
| getEnergyTransfer()         | number  | Returns max energy transfer |
| getChannel()                | number  | Returns current channel     |
| setChannel(channel: number) | nil     | Change channel to new one   |
| getMaxChannel()             | number  | Returns max channel         |
