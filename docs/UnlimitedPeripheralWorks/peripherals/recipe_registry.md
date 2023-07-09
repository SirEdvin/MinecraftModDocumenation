# Recipe registry

!!! picture inline end
    ![Recipe registry](recipe_registry.png)

??? info "Supported versions"
    **Forge**: 1.20.x
    **Fabric**: 1.20.x

!!! warning
    Current peripheral has experimental status, so API can change in future

!!! warning
    Due to nature of minecraft recipes, a lot of recipe from mods are not dispalyed correctly. You can create an [issue](https://github.com/SirEdvin/UnlimitedPeripheralWorks/issues) for to solve this.

This peripheral exists to provide help in extracting recipes from game and building complex recipe pipelines. It may not work as well as you would expect, but at least this is a start.

## Peripheral functions

| Function                                                  | Returns | Description                                  |
|-----------------------------------------------------------|---------|----------------------------------------------|
| getRecipeTypes()                                          | table   | Returns list of all recipe types in the game |
| getAllRecipesForType(recipeTypeID: string)                | table   | Returns all recipes for given recipe type    |
| getRecipeForType(recipeTypeID: string, recipeID: string)  | table   | Returns information about particular recipe  |
| getRecipesFor(itemID: string, recipeFilter: [RecipeFilter](recipe_registry.md#recipefilter)) | table   | Returns all recipe for item based on filter  |


### RecipeFilter

RecipeFilter is a specific parameter that allows you to limit recipe types.

- If recipe filter is nil or `*` it will be interpreted as "Everything allowed"
- If recipe filter is a string that contains `:` it will be interpreted as "exact this recipe type" and recipe filter value will be used to determine type
- If recipe filter is a generic string, it will be interpreted as the "Start with this script" condition.
- If recipe filter is lua table, it will be interpreted as a list of possible recipe types.
