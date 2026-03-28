# 🎮 Seasons of Nantoku - Quick Start Guide

Guía rápida para empezar a desarrollar el juego.

## 📦 Requisitos

- **Godot 4.4+** - [Descargar aquí](https://godotengine.org/download)
- **Git** - Para control de versiones

## 🚀 Primeros Pasos

### 1. Clonar o Abrir el Proyecto

```bash
# Si es la primera vez
git clone https://github.com/Fabian1803/Seasons-of-Nantoku.git
cd seasons-of-nantoku

# O abre la carpeta en Godot
```

### 2. Abrir en Godot

1. Abre **Godot 4.4**
2. Click en "Open Project" → Selecciona la carpeta del proyecto
3. ¡Listo!

### 3. Crear tu Primera Escena

1. Ve a **Scene → New Scene**
2. Selecciona un nodo raíz (ej. Node2D para 2D)
3. Nombra y guarda en `res://scenes/` (ej. `res://scenes/levels/level_1.tscn`)

### 4. Crear tu Primer Script

```gdscript
# scenes/levels/level_1.gd
extends Node2D

func _ready():
    print("¡Nivel 1 iniciado!")

func _process(delta):
    pass
```

## 📁 Estructura del Proyecto

Ver [STRUCTURE.md](STRUCTURE.md) para una guía completa.

**Resumen:**
- `scenes/` - Archivos de escenas (.tscn)
- `scripts/` - Código GDScript (.gd)
- `assets/` - Imágenes, sonidos, fuentes
- `ui/` - Interfaz de usuario
- `data/` - Configuración y datos del juego

## 🔀 Usando Git para Nuevas Características

Ver [GIT_WORKFLOW.md](GIT_WORKFLOW.md) para workflow completo.

**Quick reference:**

```bash
# Crear rama para nueva feature
git checkout -b feature/nombre-de-la-caracteristica

# Trabajar..
git add .
git commit -m "feat: description"

# Subir a GitHub
git push -u origin feature/nombre-de-la-caracteristica

# Después de aprobación, mergear en main
```

## 🎯 Tareas Comunes

### Agregar un Personaje

1. Crea escena en `scenes/characters/my_character.tscn`
2. Crea script en `scripts/characters/my_character.gd`
3. Instancia en tu nivel

### Agregar UI

1. Crea pantalla en `ui/screens/my_screen.tscn`
2. Crea script en `scripts/ui/my_screen.gd`
3. Muestra cuando sea necesario

### Agregar Assets

1. Coloca texturas en `assets/textures/`
2. Coloca sonidos en `assets/audio/`
3. Godot importará automáticamente

## 📝 Convenciones de Código

### GDScript

```gdscript
# Clases
class_name PlayerController
extends CharacterBody2D

# Variables
var health: int = 100
var speed: float = 200.0

# Constantes
const MAX_SPEED = 300.0
const ACCELERATION = 50.0

# Señales
signal health_changed(new_health)

# Métodos
func _ready():
    pass

func _process(delta):
    pass

func take_damage(amount: int):
    health -= amount
    health_changed.emit(health)
```

### Archivos

```
player_idle.png         # Sprite
level_1.tscn           # Escena
player_controller.gd   # Script
game_settings.json     # Configuración
```

## 🐛 Debugging

### Ver mensajes en consola

```gdscript
print("Mi variable: ", mi_variable)
print_debug("Debug info")
```

### Output Panel

En Godot, ve a **View → Output** para ver los logs.

## 📚 Recursos Útiles

- [Documentación Godot 4](https://docs.godotengine.org/en/stable/index.html)
- [GDScript Reference](https://docs.godotengine.org/en/stable/tutorials/scripting/gdscript/index.html)
- [Godot Tutorials](https://www.youtube.com/c/GodotEngine)

## 💡 Tips Profesionales

1. **Usa prefabs** - Reutiliza escenas pequeñas
2. **Mantén scripts cortos** - Separa responsabilidades
3. **Documenta tu código** - Usa comentarios útiles
4. **Prueba frecuentemente** - Evita sorpresas al final
5. **Haz commits útiles** - Mensajes descriptivos
6. **Organiza assets** - Mantén la estructura limpia

## 🚨 Errores Comunes

### Error: "No se encuentra la escena"

```gdscript
# ❌ Incorrecto
var scene = preload("scenes/player.tscn")

# ✅ Correcto
var scene = preload("res://scenes/characters/player.tscn")
```

### Error: "No se puede instanciar la escena"

Asegúrate de que la ruta es correcta y la escena existe.

## 🎉 ¡Listo!

Ahora estás listo para empezar a desarrollar. 

**Siguiente paso:** Crea tu primera escena y ¡diviértete!

---

**Versión:** 1.0  
**Godot:** 4.4+  
**Proyecto:** Seasons of Nantoku
