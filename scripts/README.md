# Scripts

Código GDScript organizado por funcionalidad.

## Carpetas

- **managers/** - Singletons y managers (GameManager, AudioManager, UIManager, etc.)
- **systems/** - Sistemas del juego (physics, input handling, etc.)
- **ui/** - Scripts específicos de interfaz (botones, paneles, etc.)
- **characters/** - Lógica de personajes (Player, Enemy, NPC)
- **gameplay/** - Mecánicas específicas del juego
- **utils/** - Funciones auxiliares y helpers

## Convenio de Nombres

```gdscript
# Manager (Singleton)
class_name AudioManager
extends Node

# Sistema
class_name CollisionSystem
extends Node

# Controlador
class_name PlayerController
extends CharacterBody2D

# Utilidad
class_name MathUtils
extends Node
```
