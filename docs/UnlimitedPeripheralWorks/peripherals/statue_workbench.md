# Statue workbench

!!! picture inline end
    ![Statue workbench](statue_workbench.png)

??? info "Supported versions"
    **Forge**: 1.20.x
    **Fabric**: 1.20.x

Minecraft consists of blocks, but blocks are not as flexible as many of us would like. But with the status workbench, you can overcome this problem! Just place a flexible statue on top of the workbench and be ready to shape any block that you want.


<br />

## Peripheral methods

| Function                    | Returns    | Description                                     |
|-----------------------------|------------|-------------------------------------------------|
| isPresent()                 | boolean    | Check if statue is present on top of workbench  |
| setStatueName(name: String) | nil        | Setter for statue name                          |
| getStatueName()             | string     | Returns statue name                             |
| setAuthor(author: String)   | nil        | Setter for statue author                        |
| getAuthor()                 | string     | Return statue author                            |
| setLightLevel(level: Int)   | nil        | Setter for light level of statue                |
| getLightLevel()             | Int        | Returns statue light level                      |
| setCubes(cubes: list[[Cube](statue_workbench.md#cube)]) | nil        | Setter for statue cubes                         |
| getCubes()                  | list[[Cube](statue_workbench.md#cube)] | Returns list of current cubes for statue        |
| reset()                     | nil        | Removes all information for statue and reset it |

### Cube

Cube is a table that describes the start and end points of a cube, its color, and its texture. Color is named `tint` in RGB format. Texture is basically any Minecraft texture; by default it is `peripheralworks:block/white`, so just white, that can be painted in anything via `tint`.

```lua
{
    x1 = 0,
    x2 = 14,
    y1 = 0,
    y2 = 14,
    z1 = 0,
    z2 = 14,
    tint = 0xFF00FF
}
```