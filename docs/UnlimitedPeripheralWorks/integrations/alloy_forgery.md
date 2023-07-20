# Alloy forgery

!!! picture inline end
    ![Alloy forgery](alloy_forgery.png)

??? info "Supported versions"
    **Fabric**: 1.20.x

[Alloy Forgery](https://modrinth.com/mod/alloy-forgery) adds a multiblock alloy smelter, the Alloy Forge. In its base configuration it serves as an easy way to increase ore yield, but everything is data-driven allowing you to add new forges and recipes as you please. Integration allows one to inspect meta-information about the forge as well as feed it with items and fuel and extract results.

## Supported APIs

- [inventory](https://tweaked.cc/generic_peripheral/inventory.html) API

## Peripheral methods

| Function  | Returns | Description                                                                           |
|-----------|---------|---------------------------------------------------------------------------------------|
| inspect() | table   | Returns meta information about forge, such as amount of fuel, smelt time and progress |
