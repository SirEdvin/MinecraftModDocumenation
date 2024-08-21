# Item Storage API

Generic storage API are answer for fabric transfer API for items. This API are basically copy of [fluid_storage](https://tweaked.cc/generic_peripheral/fluid_storage.html) API.

??? info "Why just don't reuse normal inventory API?"
    Main problem here is that fabric transfer API don't allow to operate any `slots`, just pushing and pulling specific items. So, there is no possible to normally simulite `inventory` API with a large amount of dirty hacks and pain
    Also, this API is quite useful for any storage, that doesn't really have slots or slots different from minecraft ones, like Drawers, AE2, Refined Storage, etc.

## Peripheral methods

| Function                                              | Returns | Description                                                                                                                                   |
|-------------------------------------------------------|---------|-----------------------------------------------------------------------------------------------------------------------------------------------|
| items(detailed?: boolean)                                               | table   | Returns a list with a detailed description for each time by default. You can pass false as the first argument to reduce information for better performance.                                                                                                         |
| pushItem(to: string, itemQuery?: [ItemQuery](introduction.md#itemquery), limit?: number    | number  | Tries to push items to target storage. Items, that will be pushed can be limited via `itemQuery` parameter and limited via `limit` parameter       |
| pullItem(from: string, itemQuery?: [ItemQuery](introduction.md#itemquery), limit?: number) | number  | Tries to pull items from target storage. Items, that will be pulled can be limited via  `itemQuery`  parameter and limited via  `limit`  parameter |
