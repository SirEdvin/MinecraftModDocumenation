# Experience API

This API is dedicated to XP manipulations: collecting it, moving out/to player and store it inside turtle.

!!! warning
    Before 1.0.0, due to ComputerCraft limitations all stored XP will be lost if you unequip turtle upgrade.

| Function                     | Returns        | Description                                                                                                                      |
|------------------------------|----------------|----------------------------------------------------------------------------------------------------------------------------------|
| getStoredXP()                | number         | Returns amount of stored XP                                                                                                      |
| getOwnerXP()                 | number         | Returns amount of owner XP                                                                                                       |
| collectXP()                  | number         | Collects XP in **interactionRadius** around turtle. Returns amount of collected XP                                               |
| suckOwnerXP(limit: number)   | [Result\[number\]](introduction.md#result) | Tries to get XP from turtle owner not more that provided limit (but can be less). Returns XP amount that was obtained from owner |
| sendXPToOwner(limit: number) | [Result\[number\]](introduction.md#result) | Tries to send XP to turtle owner not more that provided limit (but can be less). Returns XP amount that was sent to owner        |
| burnXP(limit: number)        | [Result\[number\]](introduction.md#result) | Tries to transform XP to fuel not more that provided limit (but can be less). Returns XP amount that was transformed to fuel     |
