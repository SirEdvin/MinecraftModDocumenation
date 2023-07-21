# Ultimate sensor

!!! picture inline end
    ![Ultimate sensor](ultimate_sensor.png)

??? info "Supported versions"
    **Forge**: 1.19.4, 1.20.x
    **Fabric**: 1.19.4, 1.20.x

The end goal of the ultimate sensor is to be able to sense literally anything. But for now, its scope is somewhat limited by real world and your imagination to use it.

## Supported APIs

- [Configuration API](configuration.md)
- [Operation API](operation.md)

## Peripheral methods

| Function               | Returns                                   | Description                                                                                                                                   |
|------------------------|-------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------|
| inspect("dimension")   | [Result](introduction.md#result)[string]  | Returns dimension name                                                                                                                        |
| inspect("biome")       | [Result](introduction.md#result) [string] | Returns biome name                                                                                                                            |
| inspect("weather")     | [Result](introduction.md#result) [string] | Returns weather state: rain, thunder or stable                                                                                                |
| inspect("orientation") | [Result](introduction.md#result) [number] | Returns azimuth for peripheral orientation (block orientation for block, turtle facing for turtle and player orientation for pocket computer) |
| inspect("time")        | [Result](introduction.md#result) [number] | Returns day time of world                                                                                                                     |
| inspect("light")       | [Result](introduction.md#result) [table]  | Returns information about light and sunlight of current position                                                                              |
| inspect("calendar")    | [Result](introduction.md#result) [table]  | Returns information about current day number and moon phase                                                                                   |
| inspect("chunk")       | [Result](introduction.md#result) [table]  | Returns information about current chunk: is this is slime chunk and how many ores in this chunk                                               |
| analyze("dimension")   | [Result](introduction.md#result) [table]  | Returns list of all dimension names                                                                                                           |
| listAnalyzers()        | table                                     | Returns list of all possible analyzers                                                                                                        |
| listInspectors()       | table                                     | Returns list of all possible inspectors                                                                                                       |

