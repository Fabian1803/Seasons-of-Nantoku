# UI

Interfaz de usuario organizada en pantallas y componentes.

## Carpetas

- **screens/** - Pantallas completas (MainMenu, GameHUD, PauseMenu)
- **components/** - Componentes reutilizables (botones, paneles, barras)

## Pantallas vs Componentes

### Screens (Pantallas Completas)
- Ocupan toda la pantalla
- Ejemplos: MainMenu, GameHUD, PauseMenu, SettingsScreen
- Ubicación: `ui/screens/screen_name.tscn`

### Components (Componentes)
- Elementos reutilizables dentro de pantallas
- Ejemplos: botones, paneles, health_bar, inventory_slot
- Ubicación: `ui/components/component_name.tscn`

## Estructura Recomendada

```
ui/
├── screens/
│   ├── main_menu.tscn
│   ├── game_hud.tscn
│   ├── pause_menu.tscn
│   └── settings_menu.tscn
└── components/
    ├── button.tscn              # Botón personalizado
    ├── health_bar.tscn          # Barra de vida
    ├── inventory_slot.tscn      # Slot del inventario
    └── dialogs/
        └── dialog_box.tscn      # Caja de diálogos
```

## Ejemplo de Pantalla

```gdscript
# GameHUD.gd
extends CanvasLayer

@onready var health_bar = $HBoxContainer/HealthBar
@onready var coins_label = $HBoxContainer/CoinsLabel

func _ready():
    update_ui()

func update_ui():
    health_bar.value = GameManager.player_health
    coins_label.text = "Coins: " + str(GameManager.coins)
```

## Acceso desde Código

```gdscript
# Cambiar pantalla
func show_pause_menu():
    get_tree().root.add_child(load("res://ui/screens/pause_menu.tscn").instantiate())

# Usar componente
func create_health_bar():
    var bar = load("res://ui/components/health_bar.tscn").instantiate()
    add_child(bar)
```
