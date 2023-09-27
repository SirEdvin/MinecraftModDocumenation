Since Powah supports configuration of many blocks with specific redstone mode, this API exists to allow you to modify this mode programatically.

## API methods

| Function                      | Returns | Description                                                        |
|-------------------------------|---------|--------------------------------------------------------------------|
| getRedstoneMode()             | string  | Returns current redstone mode                                      |
| setRedstoneMode(mode: string) | nil     | Setter for redstone mode, mode should be one of: ignore, on or off |
