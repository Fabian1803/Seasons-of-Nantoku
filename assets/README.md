# Assets

Recursos artísticos y multimedia del juego.

## Carpetas

- **textures/** - Texturas 2D y 3D (.png, .jpg, .exr)
- **sprites/** - Sprites y spritesheets (.png)
- **audio/** - Archivos de audio
  - **music/** - Música de fondo (.ogg, .mp3)
  - **sfx/** - Efectos de sonido (.ogg, .wav)
- **fonts/** - Fuentes personalizadas (.ttf, .otf)
- **animations/** - Animaciones de sprites/personajes
- **particles/** - Recursos para sistemas de partículas

## Convenciones de Nombres

```
player_idle_strip_8.png          # Spritesheet con 8 fotogramas
bg_music_loop.ogg                # Música
sfx_jump.wav                     # Efecto de sonido
font_arial_24.ttf                # Fuente
```

## Formatos Recomendados

- **Imágenes:** PNG (sin pérdida), JPG (con pérdida)
- **Audio:** OGG (comprimido), WAV (sin compresión)
- **Fuentes:** TTF, OTF

## Nota

Todos los archivos se importarán automáticamente en Godot. Godot creará archivos `.import` para optimización.
