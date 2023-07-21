# Jukebox
!!! picture inline end
    ![Jukebox](jukebox.png)

Pretty standart jukebox integration, that allows you to make automatic playlist.

<br class="clearBoth" />
<br class="clearBoth" />
<br class="clearBoth" />

## Peripheral methods

| Function                               | Returns | Description                                                        |
|----------------------------------------|---------|--------------------------------------------------------------------|
| getDisc()                              | table   | Returns information about stored disc or nil                       |
| replay()                               | nil     | Starts play disc again, error if no disc inside                    |
| stop()                                 | nil     | Stop playing disc                                                  |
| ejectDisc(to: string)                  | [Result](introduction.md#result)  | Tries to move disc from jukebox to target inventory                |
| injectDisc(from: string, itemQuery?: [ItemQuery](introduction.md#itemquery)) | [Result](introduction.md#result)  | Tries to move disc from target inventory to jukebox |

!!! warning
    ItemQuery scope in any case will be reduces to items with tag `minecraft:music_discs`
