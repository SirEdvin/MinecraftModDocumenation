# Applied Energistics 2

Applied Energistics 2 is a mod for [Minecraft](https://www.minecraft.net/) which contains a large amount of new content, mostly centered around the concept of using Energy, and the Transformation of Energy in a unique way. 

This integration allows you to interact with AE2 network itself, transforming some blocks (CPU cores, energy modules) into peripheral, that would provide full-featured AE2 integration.

> [!tip]- Okey, so what I can use exacly to access AE2 network peripheral?
> Any of this blocks, if they are connected to network
> 
> - Any Energy cell
> - Any crafting block: unit, co-processor or storage
> - Crystal grown accelerator

??? info "Supported versions"
    **Fabric**: 1.18, 1.19.2, 1.20.x
    **Forge**: 1.20.x

## Supported APIs

- [Item storage](item_storage.md) API for all items, that stored inside system
- [Fluid storage](https://tweaked.cc/generic_peripheral/fluid_storage.html) API for all fluids, that stored inside system
- [Energy storage](https://tweaked.cc/generic_peripheral/energy_storage.html) API for energy inside system.

## Additional peripheral methods

| Function                                                                         | Returns | Description                                                                                        |
| -------------------------------------------------------------------------------- | ------- | -------------------------------------------------------------------------------------------------- |
| getAverageEnergyDemand()                                                         | number  | Returns average energy demand of AE2 system                                                        |
| getAverageEnergyIncome()                                                         | number  | Returns average energy income for AE2 system                                                       |
| getChannelEnergyDemand()                                                         | number  | Returns amount of energy that spent for channels                                                   |
| getChannelInformation()                                                            | table   | Returns information about maxium and actual amount of channels in AE2                              |
| getCraftingCPUs()                                                                  | table   | Returns detailed information about crafting CPUS, including name, capacity, storage and occupation |
| getCraftableItems()                                                                | table   | Returns list of craftable items inside AE2 system                                                  |
| getCraftableFluids()                                                               | table   | Returns list of craftable fluids inside AE2 system                                                 |
| getPatternsFor("item", item_id: String)                                          | table   | Returns list of patterns, that exists for particual item inside AE2 system                         |
| getPatternsFor("fluid", fluid_id: String)                                        | table   | Returns list of patterns, that exists for particual fluid inside AE2 system                        |
| scheduleCrafting("item", item_id: String, amount?: number, targetCPU?: string)   | [Result](introduction.md#result)  | Try to schedule crafting for an item                                                               |
| scheduleCrafting("fluid", fluid_id: String, amount?: number, targetCPU?: string) | [Result](introduction.md#result)  | Try to schedule crafting for an fluid                                                              |

## Output examples

> [!info]- getChannelInformation example
> ```json
> {
>   "maxChannels": 8,
>   "usedChannels": 5
> }
> ```

> [!info]- getCraftingCPUs example
> ```json
> [
>   {
>       "capacity": 1,
>       "isBusy": false,
>       "storage": 262144,
>       "name": "CPUH"
>   }
> ]
> ```

> [!info]- getCraftableItems example
> ```json
> [
>   {
>       "name": "Oak Planks",
>       "technicalName": "minecraft:oak_planks"
>   }
> ]
> ```

> [!info]- getCraftableFluids example
> ```json
>   {
>       "name": "minecraft:lava"
>   }
> ```

> [!info]- getPatternsFor example
> ```json
> [
>   {
>       "inputs": [
>           {
>               "count": 1,
>               "maxStackCount": 64,
>               "name": "Oak logs",
>               "tags": {},
>               "techicalName": "minecraft:oak_log",
>               "type": "item"
>           }
>       ],
>       "outputs": [
>            {
>               "count": 4,
>               "maxStackCount": 64,
>               "name": "Oak Planks",
>               "tags": {},
>               "techicalName": "minecraft:oak_planks",
>               "type": "item"
>           }
>       ]
>   }
> ]
> ```