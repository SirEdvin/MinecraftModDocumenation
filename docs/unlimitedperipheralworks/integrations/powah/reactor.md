# Reactor

!!! picture inline end
    ![Reactor](reactor_nitro.png)

??? info "Supported versions"
    **Fabric**: 1.20.x
    **Forge**: 1.20.x

Reactors in powah are a bit special, and because of this, they have their own special integration. Take note that this integration will only work for fully built reactor.

## Supported API

- [energy_storage](https://tweaked.cc/generic_peripheral/energy_storage.html) API
- [Redstone API](powah_redstone_api.md)

## Peripheral methods

| Function              | Returns | Description                                                                                                                             |
|-----------------------|---------|-----------------------------------------------------------------------------------------------------------------------------------------|
| getEnergyTransfer()   | number  | Returns max energy transfer                                                                                                             |
| getEnergyGeneration() | number  | Returns current energy generation                                                                                                       |
| inspect()             | table   | Returns all information about generator, including amount of fuel, carbon, redstone as well as some consumption metrics and temperature |
| toggleAutoMode()      | nil     | Toggles auto mode of reactor                                                                                                            |


??? info "Example of inspect output"
    ```json
    {
        "autoMode": false,
        "currentCarbon": 0,
        "maxCarbon": 16000,
        "currentRedstone": 0,
        "maxRedstone": 18,
        "currentUranium": 0,
        "maxUranium": 1000,
        "maxSolidCoolant": 568,
        "currentSolidCoolant": 0,
        "currentTemp": 1000,
        "maxTemp": 1000,
        "energyProduction": 0,
        "uraniumConsumption": 0
    }
    ```