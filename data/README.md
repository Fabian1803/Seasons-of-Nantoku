# Data

Datos de configuración y guardado del juego.

## Carpetas

- **config/** - Archivos de configuración (settings, nivel metadata)
- **save/** - Datos de guardado de juegos

## Formatos Recomendados

- **JSON** - Datos estructurados legibles
- **CSV** - Tablas (diálogos, enemigos, items)
- **Binary** - Datos comprimidos (para saves finales)

## Ejemplo de Estructura

```
data/
├── config/
│   ├── game_settings.json       # Configuración del juego
│   ├── levels_metadata.json     # Información de niveles
│   ├── items.csv                # Catálogo de items
│   └── enemies.csv              # Estadísticas de enemigos
└── save/
    ├── slot_1.json              # Guardado de jugador 1
    ├── slot_2.json              # Guardado de jugador 2
    └── slot_3.json              # Guardado de jugador 3
```

## Acceso desde GDScript

```gdscript
# Cargar JSON
func load_config():
    var file = FileAccess.open("res://data/config/game_settings.json", FileAccess.READ)
    return JSON.parse_string(file.get_as_text())

# Guardar JSON
func save_game(data):
    var json_string = JSON.stringify(data)
    var file = FileAccess.open("user://save/slot_1.json", FileAccess.WRITE)
    file.store_string(json_string)
```

**Nota:** Usa `res://` para datos de lectura. Usa `user://` para datos de guardado (carpeta de usuario).
