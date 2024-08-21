# Blaze burner

!!! picture inline end
    ![Blaze burner](blaze_burner.png)

??? info "Supported versions"
    **Fabric**: 1.20.x
    **Forge**: 1.20.x

Special intergration for blaze burner! Not much, but you can check fuel type and how long it would burn. `fuelType` can be "none", "normal" or "special" and `remainingBurnTime` is time left to burn in server ticks, not seconds.

<br class="clearBoth" />

## Peripheral methods

| Function                    | Returns | Description                 |
|-----------------------------|---------|-----------------------------|
| inspect()         | table  | Returns table with `fuelType` and `remainingBurnTime` values |
