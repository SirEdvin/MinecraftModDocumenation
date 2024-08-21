# Actuators

!!! picture inline end
    ![rope pulley](rope_pulley.png)

??? info "Supported versions"
    **Fabric**: 1.20.x
    **Forge**: 1.20.x

Actuators, such as rope pulleys, also have an extra method, that allows you to understand their speed and if they are running.

<br class="clearBoth" />
<br class="clearBoth" />
<br class="clearBoth" />

## Peripheral methods

| Function                    | Returns | Description                 |
|-----------------------------|---------|-----------------------------|
| inspect()         | table  | Returns table with `movementSpeed` and `isRunning` information|
