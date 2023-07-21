# Shooting turtle

!!! picture inline end
    ![Shooting turtle](bow_turtle.png)

??? info "Supported versions"
    **Fabric**: 1.19.4, 1.20.x
    **Forge**: 1.19.4, 1.20.x


Maybe someone had a dream about turtle, finally shooting items from a bow? Well, now this dream come true. This turtle now capable of sending any items to the sky (or little closer).

If the item hits any block or entity with inventory, it will be automatically stored in it. If the item is an arrow, it will be shot as an arrow from the dispenser.

Of course, the item can just hit the ground and after some time will be available to pickup as a regular item on the ground.

## Supported APIs

- [Configuration API](configuration.md)
- [Fuel API](fuel.md)
- [Operation API](operation.md)

## Peripheral methods

| Function                                                          | Returns | Description                                                                                                                         |
|-------------------------------------------------------------------|---------|-------------------------------------------------------------------------------------------------------------------------------------|
| getAngle()                                                        | number  | Returns current bow angle                                                                                                           |
| setAngle(angle:number)                                            | nil     | Set bow angle to new value                                                                                                          |
| shoot(power: number, limit?:number, suppressExtraLogic?: boolean) | [Result](introduction.md#result)  | Tries to shoot item. If item is arrow and suppressExtraLogic is false, item will be shot like arrow instead of just item projectile |
