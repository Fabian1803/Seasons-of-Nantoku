# Scenes

Archivos de escenas (.tscn) organizados por tipo.

## Carpetas

- **levels/** - Escenas de niveles del juego
- **characters/** - Escenas de personajes controlables y NPCs
- **objects/** - Objetos interactivos del mundo (cajas, enemigos, etc.)
- **ui/** - Pantallas de UI complejas (menús, HUDs, etc.)

## Nota Importante

Las **escenas pequeñas reutilizables** (prefabs) van en la carpeta `prefabs/`, no aquí.
Las escenas en esta carpeta son generalmente más grandes y específicas del juego.

## Ejemplo de Estructura

```
scenes/
├── levels/
│   ├── level_1.tscn
│   ├── level_2.tscn
│   └── main_scene.tscn
├── characters/
│   ├── player.tscn
│   └── enemy_types/
└── objects/
    ├── chest.tscn
    └── trap.tscn
```
