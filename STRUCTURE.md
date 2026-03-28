# Estructura del Proyecto - Seasons of Nantoku

Guía profesional de la estructura del proyecto Godot 4.4

## 📁 Estructura de Carpetas

```
seasons-of-nantoku/
│
├── 🎬 scenes/                 # Escenas principales del juego
│   ├── levels/                # Archivos de escenas para niveles
│   ├── characters/            # Escenas de personajes
│   ├── objects/               # Objetos interactivos del mundo
│   └── ui/                    # Pantallas de UI complejas
│
├── 📝 scripts/                # Código GDScript organizado
│   ├── managers/              # Singletons (GameManager, AudioManager, etc.)
│   ├── systems/               # Sistemas del juego (physics, collision, etc.)
│   ├── ui/                    # Scripts específicos de interfaz
│   ├── characters/            # Lógica de personajes
│   ├── gameplay/              # Mecánicas de juego
│   └── utils/                 # Funciones auxiliares y helpers
│
├── 🎨 assets/                 # Todos los resources artísticos
│   ├── textures/              # Texturas 2D y 3D
│   ├── sprites/               # Sprites y spritesheets
│   ├── audio/
│   │   ├── music/             # Música de fondo
│   │   └── sfx/               # Efectos de sonido
│   ├── fonts/                 # Fuentes personalizadas
│   ├── animations/            # Animaciones (PNG sequences, etc.)
│   └── particles/             # Efectos de partículas
│
├── 🔧 prefabs/                # Nodos reutilizables (mini-escenas)
│   ├── characters/            # Prefabs de personajes
│   ├── objects/               # Prefabs de objetos
│   └── ui/                    # Componentes de UI reutilizables
│
├── 📍 levels/                 # Archivos de datos de niveles
│   └── (nivel1.json, etc.)    # Configuración declarativa de niveles
│
├── 🎮 ui/                     # Componentes y pantallas UI
│   ├── screens/               # Pantallas completas (Menu, HUD, etc.)
│   └── components/            # Componentes reutilizables
│
└── 💾 data/                   # Datos del juego
    ├── config/                # Archivos de configuración (JSON, CSV)
    └── save/                  # Datos de guardado de juegos
```

## 🎯 Guía de Uso por Carpeta

### `scenes/`
- **Qué va aquí:** Archivos `.tscn` (escenas de Godot)
- **Ejemplo:** `scenes/levels/level_1.tscn`, `scenes/characters/player.tscn`
- **Nota:** Las escenas grandes van aquí; los componentes pequeños van en `prefabs/`

### `scripts/`
- **Qué va aquí:** Código GDScript (`.gd`)
- **Subcarpetas:**
  - `managers/`: GameManager, UIManager, AudioManager (accesibles globalmente)
  - `systems/`: Sistemas del juego (no instanciados directamente)
  - `ui/`: Scripts de botones, paneles, etc.
  - `characters/`: Lógica de Player, Enemy, NPC
  - `gameplay/`: Mecánicas específicas del juego
  - `utils/`: Helpers, funciones auxiliares

### `assets/`
- **Qué va aquí:** Todo recurso artístico
- **Subdivisiones claras:**
  - Imágenes: `textures/`, `sprites/`
  - Audio: `audio/music/`, `audio/sfx/`
  - Fuentes: `fonts/`
  - Efectos: `animations/`, `particles/`

### `prefabs/`
- **Qué va aquí:** Escenas pequeñas reutilizables (componentes)
- **Ejemplo:** `prefabs/ui/button.tscn`, `prefabs/objects/coin.tscn`
- **Ventaja:** Instancia las mismas escenas en múltiples lugares sin duplicar

### `ui/`
- **Qué va aquí:** Escenas y scripts de interfaz
- **Separación:**
  - `screens/`: Pantallas completas (MainMenu, PauseMenu, GameHUD)
  - `components/`: Botones, paneles, barras de vida (pequeños componentes)

### `data/`
- **Qué va aquí:** Configuración y datos
- **Ejemplo:** 
  - `data/config/game_settings.json`
  - `data/save/player_save_slot_1.json`

## 🔄 Workflow Recomendado

1. **Crear una escena** → Guardar en `scenes/`
2. **Si es reutilizable** → Mover a `prefabs/` e instanciar desde ahí
3. **Crear un script** → Guardar en `scripts/<categoria>/`
4. **Agregar arte** → Organizar en `assets/<tipo>/`
5. **Datos de configuración** → Guardar en `data/`

## 📌 Naming Conventions (Convenciones de Nombres)

### Para Archivos
- **Escenas:** `player.tscn`, `enemy_zombie.tscn`
- **Scripts:** `player_controller.gd`, `audio_manager.gd`
- **Assets:** `player_idle.png`, `bg_music.ogg`

### En GDScript
- **Clases:** `PascalCase` (class_name PlayerController)
- **Variables:** `snake_case` (var health_points = 100)
- **Constantes:** `UPPER_CASE` (const MAX_SPEED = 200)
- **Señales:** `snake_case_with_action` (signal health_changed)

## 🎯 Escalabilidad

Esta estructura soporta:
- ✅ Proyectos pequeños (1-2 desarrolladores)
- ✅ Proyectos medianos (3-5 desarrolladores)
- ✅ Fácil expansión (agregar más niveles, personajes, etc.)

## 💡 Tips Profesionales

1. **Usa escenas anidadas:** No hagas todo en una sola escena
2. **Reutiliza prefabs:** Evita duplicar código y escenas
3. **Separa lógica de presentación:** Scripts en `scripts/`, escenas visuales en `scenes/`
4. **Versionado de datos:** Guarda configuraciones en JSON/CSV en `data/`
5. **Documentación:** Crea archivos README en subcarpetas si es necesario

---

**Creado para:** Seasons of Nantoku (Godot 4.4)
