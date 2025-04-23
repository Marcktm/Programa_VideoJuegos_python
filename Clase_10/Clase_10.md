
# 📘 Clase 10 – Sonidos del juego

## 🎯 Objetivos
- Entender cómo se reproducen sonidos en videojuegos.
- Usar `pygame.mixer` para añadir efectos de sonido y música.
- Integrar sonidos de inicio, colisión y motor al juego.

---

## 🧠 Contenidos Teóricos

### ¿Qué es un motor de sonido?
Un motor de sonido permite cargar y reproducir archivos de audio durante la ejecución del juego.

### ¿Qué es `pygame.mixer`?
Es un módulo de Pygame para manejar audio. Se debe inicializar al comienzo:

```python
import pygame
pygame.mixer.init()
```

---

## 💻 Actividad práctica

### 1. Inicializar sonidos (`sounds.py`)

```python
endingMusic = pygame.mixer.Sound("sounds/game_over.wav")
startingMusic = pygame.mixer.Sound("sounds/game_start.wav")
motorIdle = pygame.mixer.Sound("sounds/motor_player.wav")
motorAccelerated = pygame.mixer.Sound("sounds/motor_player_accelerated.wav")
```

### 2. Reproducir sonido

```python
startingMusic.play()
motorIdle.play(-1)  # Reproduce en loop
motorIdle.stop()
```

### 3. Integrar sonidos en `game.py`

Reproducir el motor al acelerar:

```python
if accelerated:
    motorAccelerated.play()
else:
    motorIdle.play()
```

O detener todos:

```python
def stopAllSounds():
    endingMusic.stop()
    startingMusic.stop()
    motorIdle.stop()
    motorAccelerated.stop()
```

---

## ✅ Tareas

- Probar distintos sonidos para motor, colisiones y power-ups.
- Cambiar los sonidos por otros archivos `.wav`.
- Agregar una condición para que el sonido del motor no se solape.

---

## 🛠 Archivos utilizados
- `sounds.py`
- `game.py`

## 🎵 Recomendaciones
- Los archivos de sonido deben estar en formato `.wav`.
- Guardarlos en una carpeta `sounds/` dentro del proyecto.

## 🧩 Requiere comprensión de:
- Reproducción de audio en Pygame
- Eventos y condiciones dentro del juego
