# Protective automata

!!! picture inline end
    ![Protective automata](protective_automata.png)


??? info "Supported versions"
    **Forge**: 1.19.4, 1.20.x
    **Fabric**: 1.19.4, 1.20.x

Advanced automata that can harness power of the iron golem to protect. This automata provider extra capabilities of take care of hostile mobs.

## Obtaining

Feed 1 iron golem soul to [automata core](automata.md) with [soul scrapper](soul_scrapper.md) to obtain it.

## Supported APIs

- [Configuration API](configuration.md)
- [Fuel API](fuel.md)
- [Operation API](operation.md)
- [Look API](look.md)
- [Suck API](suck.md)
- [Interaction API](interaction.md): allows interaction with blocks and some entities
- [Scan API](scan.md): allows interaction with items and some entities
- [Capture API](capture.md): only interaction with some entities
- [AI API](ai.md): only interaction with some entities

## Notes

> [!tip]- Which entity are usable for protective automata
> If all of criteria are met:
> - Entity is hostile
> - Entity doesn't have "creature" category
> - Entity doesn't have `turtlematic:husbandry_extra_animal` tag
