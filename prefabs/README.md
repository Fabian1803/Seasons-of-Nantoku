# Prefabs

Escenas pequeñas reutilizables (componentes).

## Concepto

Un prefab es una **escena pequeña que instancias múltiples veces**.

**Ventajas:**
- No duplicas código
- Cambios en el prefab se aplican a todas las instancias
- Más organizado y mantenible

## Carpetas

- **characters/** - Prefabs de personajes (enemigos, NPCs)
- **objects/** - Prefabs de objetos (monedas, cajas, trampas)
- **ui/** - Componentes UI reutilizables (botones, paneles)

## Ejemplo

```gdscript
# En tu escena principal
@onready var coin_scene = preload("res://prefabs/objects/coin.tscn")

func spawn_coin(position):
    var coin = coin_scene.instantiate()
    coin.position = position
    add_child(coin)
```

## Diferencia: Scenes vs Prefabs

| Aspect | Scenes | Prefabs |
|--------|--------|---------|
| Tamaño | Más grande | Más pequeño |
| Reutilización | Una sola vez | Múltiples veces |
| Ubicación | `scenes/` | `prefabs/` |
| Ejemplo | level_1.tscn | coin.tscn |
