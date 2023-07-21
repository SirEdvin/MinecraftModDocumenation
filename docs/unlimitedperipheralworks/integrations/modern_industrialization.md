# Modern Industrialization

[Modern Industrialization](https://www.curseforge.com/minecraft/mc-mods/modern-industrialization) is a standalone tech mod, where the unltimate objective is TOTAL AUTOMATION, and with help of this ComputerCraft integration you will be able to achive it more quicky!

??? info "Supported versions"
    **Fabric**: 1.18, 1.19.2

## Enegry integration

So, every block, that can hold energy in MI now will provide [energy_storage](https://tweaked.cc/generic_peripheral/energy_storage.html) peripheral. Take a note, that values returned by this peripheral are using EU. 

## Crafting machine peripheral

For crafting machines, such as furnaces, you will be able to review recipe progress as well as overclocking stats. 

### Peripheral methods

| Function                 | Returns | Description                                         |
| ------------------------ | ------- | --------------------------------------------------- |
| isBusy()                 | boolean | Returns true if machine is now active               |
| getCraftingInformation() | table   | Returns detailed information about crafting process |
