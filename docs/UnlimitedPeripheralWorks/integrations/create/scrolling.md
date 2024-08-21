# Scrolling

!!! picture inline end
    ![Hose pulley](hose_pulley.png)

??? info "Supported versions"
    **Fabric**: 1.20.x
    **Forge**: 1.20.x

This integration works with most blocks in Create that have a scrolling value setting, and it allows you to manipulate this setting from the computer. While it is a number, it also works for a lot of mod switch logic, like one with a hose pulley, because these options are also encoded like 0, 1, and 2.

<br class="clearBoth" />

## Peripheral methods

| Function                    | Returns | Description                 |
|-----------------------------|---------|-----------------------------|
| getScrollValue()         | number  | Returns current value of setting |
| setScrollValue(value: number)       | void  | Set a value to the scrolling option. If the value is too high or too low, the maximum or minimum option would be used instead.     |
