# 🚀 Git Workflow - Feature Branches

Guía para desarrollar nuevas características de forma profesional usando **Git Features/Branches**.

## ¿Qué es una Feature Branch?

Una **feature branch** (rama de características) es una rama de Git donde trabajas en una **nueva funcionalidad aislada** sin afectar el código principal (`main`).

### Ventajas

✅ **Desarrollo independiente** - Cada feature en su propia rama  
✅ **Sin conflictos** - Los cambios están aislados  
✅ **Fácil de revertir** - Si algo sale mal, elimina la rama  
✅ **Code review** - Puedes hacer pull requests para revisar cambios  
✅ **Historial limpio** - El historial de commits es claro y organizado  

## 📋 Workflow Recomendado

### 1. Crear una Feature Branch

```bash
# Asegúrate de estar en main y estar actualizado
git checkout main
git pull origin main

# Crea una nueva rama para tu feature
git checkout -b feature/nombre-de-la-caracteristica
```

### 2. Ejemplos de Nombres de Ramas

```bash
# Implementar sistema
feature/game-manager          # Nueva funcionalidad importante
feature/player-movement       # Movimiento del jugador
feature/ui-main-menu          # Interfaz del menú principal

# Ejemplos más específicos
feature/add-enemy-ai          # Agregar IA de enemigos
feature/implement-save-system # Sistema de guardado
feature/add-audio-manager     # Gestor de audio

# Otras ramas
bugfix/fix-player-collision   # Corrección de bugs
docs/update-readme            # Documentación
```

### 3. Trabajar en la Feature

```bash
# Hacer cambios, crear archivos, scripts, etc.

# Agregar cambios al staging
git add .

# Hacer commits descriptivos
git commit -m "feat: Add player movement controller

- Implement CharacterBody2D with input handling
- Add jumping mechanics
- Add speed limits and acceleration"

# Hacer más commits si es necesario
git commit -m "feat: Add player animation states

- Add idle animation
- Add running animation
- Add jumping animation"
```

### 4. Mantener Actualizada la Feature Branch

Si otros han hecho push a `main`, actualiza tu rama:

```bash
# Traer cambios de main
git fetch origin
git rebase origin/main

# O si prefieres merge (menos limpio, pero más seguro)
git merge origin/main
```

### 5. Subir la Feature a GitHub

```bash
# Primera vez
git push -u origin feature/nombre-de-la-caracteristica

# Siguientes veces
git push
```

### 6. Crear un Pull Request (PR)

En GitHub:
1. Ve a tu repositorio
2. Verás un botón "Compare & pull request"
3. Llena el título y descripción
4. Haz push de la PR

**Ejemplo de descripción:**

```
## Descripción

Implementa el sistema de movimiento del jugador.

## Cambios

- Agregar PlayerController.gd (script de jugador)
- Crear escena player.tscn
- Agregar sprites de animación
- Implementar input handling (movimiento y salto)

## Testing

- ✅ Movimiento izquierda/derecha funciona
- ✅ Salto funciona correctamente
- ✅ Colisiones funcionan
```

### 7. Después de Aprobación: Mergear a Main

En GitHub, puedes hacer click en "Merge pull request", o desde terminal:

```bash
git checkout main
git pull origin main
git merge feature/nombre-de-la-caracteristica
git push origin main

# Eliminar la rama (opcional, pero recomendado)
git branch -d feature/nombre-de-la-caracteristica
git push origin --delete feature/nombre-de-la-caracteristica
```

## 💾 Commit Message Convention

Usa [Conventional Commits](https://www.conventionalcommits.org/) para mensajes claros:

```
feat:      Nueva característica
fix:       Corrección de bug
docs:      Cambios en documentación
style:     Cambios de formato (sin cambios de lógica)
refactor:  Refactorizar código
perf:      Mejoras de rendimiento
test:      Agregar tests
```

### Ejemplos

```bash
git commit -m "feat: Add pause menu functionality"
git commit -m "fix: Player collision with walls"
git commit -m "docs: Update README with controls"
git commit -m "refactor: Extract UI components to prefabs"
```

## 🔀 Casos Comunes

### Caso 1: Necesitas cambios de otra rama

```bash
git checkout feature/tu-rama
git merge feature/otra-rama    # O rebase si prefieres
```

### Caso 2: Accidentalmente vinculaste en main

```bash
# NO HAGAS PUSH!
git reset HEAD~1                # Deshacer último commit
git checkout -b feature/oops    # Crear rama
git push -u origin feature/oops
```

### Caso 3: Quieres eliminar tu rama local

```bash
git branch -d feature/nombre     # Eliminar rama local
git push origin --delete feature/nombre  # Eliminar en GitHub
```

## 📊 Ejemplo Visual de Workflow

```
main              feature/player-movement

●  (v1.0)
│
├─────────●  (WIP: Add movement)
│         │
│         ├─●  (Add jump)
│         │ │
│         └─●  (Add animations)
│
├─────────●  (Merge PR)
│
●  (v1.1)
```

## ✅ Checklist Antes de Hacer Push

- [ ] Los cambios están en una rama aparte (`git status`)
- [ ] He hecho commits descriptivos (`git log`)
- [ ] Probé que el código funciona (sin errores en Godot)
- [ ] Actualicé la rama con cambios de main (`git pull origin main`)
- [ ] Eliminé archivos innecesarios (`.godot/`, archivos temporales)

## 🎯 Ejemplo Práctico Completo

```bash
# 1. Crear rama
git checkout main
git pull origin main
git checkout -b feature/add-enemy-ai

# 2. Trabajar en la feature
# ... Creas enemy_ai.gd, enemy.tscn, etc.

git add scripts/characters/enemy_ai.gd
git commit -m "feat: Add enemy AI system

- Implement pathfinding
- Add state machine (idle, chase, attack)
- Add detection radius"

git add scenes/characters/enemy.tscn
git commit -m "feat: Create enemy scene with AI

- Add CollisionShape2D
- Add Sprite2D
- Add enemy_ai.gd script"

# 3. Subir a GitHub
git push -u origin feature/add-enemy-ai

# 4. En GitHub → Crear Pull Request
# 5. Revisión y aprobación
# 6. Mergear en main

git checkout main
git pull origin main
git merge feature/add-enemy-ai
git push origin main
```

---

**Resumen:** Las branches de features te permiten trabajar de forma aislada y profesional. ¡Úsalas siempre! 🚀
