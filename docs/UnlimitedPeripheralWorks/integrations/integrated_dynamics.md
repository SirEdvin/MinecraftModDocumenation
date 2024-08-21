# Integrated Dynamics

!!! picture inline end
    ![Integrated dynamics](integrated_dynamics.png)

??? info "Supported versions"
    **Forge**: 1.19.4, 1.20.x

[Integrated Dynamics](https://www.curseforge.com/minecraft/mc-mods/integrated-dynamics) is a mod that requires you to build networks for complex automation and system integration. It is a mix between bundled redstone, BuildCraft gates, and Applied Energistics-style networks.

## Bidirectional communication with Integration Dynamics network

!!! info
    This type of communication implemented at 1.4.4 version, replacing old file-based communication

!!! warning

    Data that is written by a computer is not persistent and would be wiped by server restarts.

This type of communication allows you to connect to a computer via Machine Reader/Writer ID blocks. Each computer now has access to the new LuaAPI - `integrated_dynamics`, which contains three very easy-to-understand methods.

| Function                 | Returns | Description                                         |
| ------------------------ | ------- | --------------------------------------------------- |
| getInput()                 | any | Returns value that was written to computer by Machine Writer               |
| getOutput() | string   | Returns value that was written by computer to Machine Reader |
| setOutput(json: string) | void   | Writes value to Machine Reader, value should be a dictionary encoded as json |

## Extracting data from Integrated Dynamics

For this goal, you can use Variable Store from Integrated Dynamics. By default, this store serves as a generic inventory. Integration modifies generic inventory methods to take variables into account.

For example, if you run `list()`, you will receive enriched output

```lua
{
    id = 1,
    type = "nbt",
    isDynamic = false,
    label = "MyCuteVariable"
}
```

To get the actual variable value, you can use `getItemDetail(slot: int)` method, which will calculate and return information about the variable in the required slot

```lua
{
    id = 0,
    type = "nbt",
    isDynamic = false,
    label = "MyCuteVariable",
    value = {
        v = {
            ["test.lua"] = "THERE IS NO DATA HERER"
        }
    }
}
```

## Sending data to Integrated Dynamics network

!!! warning

    This logic works only for UnlimitedPeripheralWorks 1.4.3 and less.

Integration also provides a specific aspect for Machine Reader, called "Directory inside computer". This output has an NBT type and will read data from any file inside "/integrateddynamics" folder in the target computer and return it to the ID network as an NBT. All files should be utf-8 encoded.

!!! note "Example output"
    ```json
    {
        "file_name_1": "file_content_1",
        "file_name_2": "file_content_2"
    }
    ```