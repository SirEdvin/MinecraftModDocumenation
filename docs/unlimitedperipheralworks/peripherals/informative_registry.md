# Informative registry

!!! picture inline end
    ![Informative registry](informative_registry.png)

??? info "Supported versions"
    **Forge**: 1.20.x
    **Fabric**: 1.20.x


Ever wonder how many blocks or items exist on a server with so many mods? Now you can access them all. This peripheral allows you to access this information and game and probably do something interesting with it.

<br />

## Peripheral functions

| Function                            | Returns | Description                               |
|-------------------------------------|---------|-------------------------------------------|
| list("item")                        | table   | Returns list of all possible item IDs     |
| list("block")                       | table   | Returns lists of all possible block IDs   |
| list("fluid")                       | table   | Returns lists of all possible fluid IDs   |
| list("list")                        | table   | Returns lists of all possible list IDs    |
| describe("item", itemID: string)    | table   | Returns detailed information about items  |
| describe("block", blockID: string)  | table   | Returns detailed information about block  |
| describe("fluid ", fluidID: string) | table   | Returns detailed information about fluid  |
| describe("list", listID: string)    | string  | Returns text description of specific list |