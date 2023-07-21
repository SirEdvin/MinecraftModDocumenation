# Occultism

[Occultism](https://www.curseforge.com/minecraft/mc-mods/occultism) is a Minecraft magic mod built around summoning demons and interacting with them.

??? info "Supported versions"
    **Forge**: 1.19.4, 1.20.x

## Occultism Storage

With this integration, occultism storage will provide [Item Storage API](item_storage.md) with a few extra methods

### Peripheral methods

| Function                    | Returns | Description                                                     |
|-----------------------------|---------|-----------------------------------------------------------------|
| getMaxSlots()               | number  | Returns max slots in storage                                    |
| getUsedSlots()              | number  | Returns used slots in storage                                   |
| isBlacklisted(item: string) | boolean | Returns true if the item is blacklisted in storage, false otherwise |

## Golden sacrificial bowl

Unfortunately, for now, automation of occultism rituals is not supported, but when using a golden sacrificial bowl as a peripheral you can observe the flow of ritual

### Peripheral methods

| Function                 | Returns      | Description                                                                         |
|--------------------------|--------------|-------------------------------------------------------------------------------------|
| isBusy()                 | boolean      | Returns true if ritual in progress                                                  |
| getCraftingInformation() | table or nil | Returns information about the current ritual if there is one in progress, nil otherwise |
