# Soul scrapper

!!! picture inline end
    ![Soul scrapper turtle](soul_scrapper.png)

Terrible tool, that allows you to infuse an item in a selected slot with soul of any mob, that you will find on the way.

> [!info] What I can infuse?
> Currently, only [automata core](automata.md) can be infused

<br class="clearBoth" />
<br class="clearBoth" />
<br class="clearBoth" />

| Function           | Returns | Description                                                                        |
|--------------------|---------|------------------------------------------------------------------------------------|
| harvestSoul()      | [Result](introduction.md#result)  | Tries to harvest entity soul at line of sight of turtle into item in selected slot |
| getLeftEntities()  | table or nil, string or nil | Tries to get information about left entities to fill soul. Returns table if item in selected slot have started consuming soul and nil with error otherwise

> [!tip]- getLeftEntities output examples
> ```json
> [
>     {"name": "Cow", "leftCount": 1},
>     {"name": "Sheep", "leftCount": 1},
>     {"name": "Pig", "leftCount": 1}
> ]
> ```
