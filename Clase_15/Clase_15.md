
# 📘 Clase 15 – Personalización y toque final

## 🎯 Objetivos
- Permitir que cada alumno personalice su versión del juego.
- Modificar sprites, sonidos y otros elementos visuales.
- Ajustar dificultad, velocidad y otros parámetros del juego.
- Preparar la versión final para presentar.

---

## 🧠 Contenidos Teóricos

### ¿Qué es personalizar un videojuego?
Consiste en adaptar visual y funcionalmente un juego para que tenga estilo propio. Esto mejora el compromiso y motiva la creatividad.

Áreas comunes para personalizar:
- Sprites e imágenes
- Fondos y estética
- Sonidos y música
- Dificultad y velocidad

---

## 💻 Actividad práctica

### 1. Cambiar sprites
Modificar las imágenes en la carpeta `images/`:

```python
self.image = pygame.image.load("../images/mi_auto.png").convert_alpha()
```

Asegurarse de mantener los tamaños adecuados (`50x50` px por ejemplo).

---

### 2. Cambiar sonidos

En `sounds.py`, cambiar la ruta:

```python
motorIdle = pygame.mixer.Sound("sounds/mi_motor.wav")
```

Probar que el formato sea `.wav` para compatibilidad.

---

### 3. Ajustar dificultad

Modificar velocidad, número de enemigos, tiempo de aparición:

```python
if frame_count % 100 == 0:  # más enemigos
    ...
```

O modificar `self.speed` en los enemigos:

```python
enemy.speed = 7  # más rápido
```

---

### 4. Cambiar colores, texto, nombre del juego

En `screen.py` o `main.py`:

```python
pygame.display.set_caption("Mi Juego Increíble")
```

---

## ✅ Tareas

- Personalizar al menos un sprite, un sonido y un parámetro de dificultad.
- Cambiar el título del juego y nombre del archivo final.
- Comprimir la carpeta final para enviarla como entrega.

---

## 🛠 Archivos utilizados
- `screen.py`
- `player.py`, `enemy.py`, `powerup.py`
- `sounds.py`
- `images/` y `sounds/` (carpetas de recursos)

## 🧩 Requiere comprensión de:
- Manejo de archivos
- Modificación de parámetros
- Creatividad y pruebas
