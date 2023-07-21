# Generators

!!! picture inline end
    ![Ender cell](ender_cell_nitro.png)

??? info "Supported versions"
    **Fabric**: 1.20.x
    **Forge**: 1.20.x

This integration works with any powah generator (aside from reactors, which have their own integration), and it allows you to inspect additional information about generators, including current energy generation.

## Supported API

- [energy_storage](https://tweaked.cc/generic_peripheral/energy_storage.html) API
- [Redstone API](powah_redstone_api.md)

## Peripheral methods

| Function                    | Returns | Description                 |
|-----------------------------|---------|-----------------------------|
| getEnergyTransfer()         | number  | Returns max energy transfer |
| getEnergyGeneration()       | number  | Returns current energy generation     |
