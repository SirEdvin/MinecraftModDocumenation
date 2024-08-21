# Filters

!!! picture inline end
    ![Brass funnel](brass_funnel.png)

??? info "Supported versions"
    **Fabric**: 1.20.x
    **Forge**: 1.20.x

This integration works with most blocks in Create that have a filter component, and it allows you to manipulate this filter from the computer.

<br class="clearBoth" />
<br class="clearBoth" />
<br class="clearBoth" />

## Peripheral methods

| Function                    | Returns | Description                 |
|-----------------------------|---------|-----------------------------|
| getFilterName()         | string  | Returns item ID of current filter |
| setFilterName(itemID: string)       | void  | Set filter to itemID. Would throw exception in case of incorrect itemID     |
| clearFilterItem()       | void  | Clear any filtering     |
