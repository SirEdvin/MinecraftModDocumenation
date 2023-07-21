# Nature's Compass

With this integration, you can use Nature's Compass as an upgrade for turtle and pocket computers!

??? info "Supported versions"
    **Fabric**: 1.19.4, 1.20.x
    **Forge**: 1.19.4, 1.20.x

### Peripheral methods

| Function                      | Returns                          | Description                                                                                |
|-------------------------------|----------------------------------|--------------------------------------------------------------------------------------------|
| getBiomes()                   | table                            | Returns a list of biomes IDs available to search in this dimension                            |
| scheduleSearch(biome: string) | [Result](introduction.md#result) | Tries to run search for specific biome id. Will fail if another search is not finished yet |
| getState()                    | string                           | Returns current search state, which can be one of INACTIVE, SEARCHING, FOUND, NOT_FOUND         |
| getResult()                   | table                            | Returns information about found biome or nil, if no biome found                            |

!!! note

    The result of the search is position and facing dependent as in [Scan API](scan.md). You don't need to re-run the search after changing position or facing, coordinates will update automatically on the next `getResult()` function call.

??? tip "getResult() output example"
    ```json
    {
        "x": 12,
        "z": 0,
        "distance": 12,
        "biome": "minecraft:badlands"
    }
    ```
