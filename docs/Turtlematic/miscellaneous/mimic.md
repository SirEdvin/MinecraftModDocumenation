# Mimic

!!! picture inline end
    ![Mimic turtle](mimic_turtle.png)

??? info "Supported versions"
    **Fabric**: 1.20.x
    **Forge**: 1.20.x

Mimic turtle as you would expect, can mimic any block in the game. Even if a block has custom rendering (in most cases). So, do you want to scare your friend or maybe just built a flying elevator? Now it is completely possible.

<br />

## Peripheral methods

| Function                                      | Returns                         | Description                                                                                                                                         |
|-----------------------------------------------|---------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------|
| setTransformation(rml: [RML](introduction.md#rml))                | nil                             | Setter for transformation instructions                                                                                                              |
| getTransformation()                           | [RML](introduction.md#rml) or nil                   | Returns current transformation instructions                                                                                                         |
| setMimic(block: [BlockState](introduction.md#blockstate), nbtData?: string) | nil                             | Setter for mimic block. nbtData will be used for loading information into fake block entity for rendering. NBT data should be passed as JSON string |
| getMimic()                                    | [BlockState](introduction.md#blockstate) or nil, table or nil | Returns pair of current mimic block state and table with nbt data                                                                                   |
| reset()                                       | nil                             | Resets mimic turtle                                                                                                                                 |