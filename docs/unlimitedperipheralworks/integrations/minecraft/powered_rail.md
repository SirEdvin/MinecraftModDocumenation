# Powered rail

!!! picture inline end
    ![Powered rail](powered_rail.png)

There is a very problematic to hook up minecart with computer craft. This integration should help a lot. Finally, automatic item transferring via minecarts are possible!

> [!info]
> Powered rail peripheral will provide same API methods like [inventory](https://tweaked.cc/generic_peripheral/inventory.html) from ComputerCraft integrations for aggregated inventory of ALL minecarts on rail. So, if there is three chest minecarts on rail, inventory `size()` will return 81.

## Peripheral methods

| Function                         | Returns | Description                                                            |
|----------------------------------|---------|------------------------------------------------------------------------|
| isPowered()                      | boolean | Returns true if powered rails are enabled                              |
| getMinecarts()                   | table   | Returns list of minecarts                                              |
| pushMinecarts(reverse?: boolean) | nil     | Pushes all minecarts in a rail forward or backward if reserve are true |
