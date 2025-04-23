
# 📘 Clase 12 – Sistema de vidas con RainbowCar

## 🎯 Objetivos
- Implementar un sistema para ganar vidas al recolectar un objeto especial.
- Usar colisiones para detectar la interacción con el auto multicolor (`RainbowCar`).
- Limitar la cantidad máxima de vidas del jugador.

---

## 🧠 Contenidos Teóricos

### ¿Qué es un sistema de vidas?
Las **vidas** representan la cantidad de errores que un jugador puede cometer antes de perder.

Agregar vidas permite dar una segunda oportunidad y recompensar el buen desempeño.

---

## 💻 Actividad práctica

### 1. Crear el enemigo `RainbowCar`

En `enemy.py` y `EnemyFactory`:

```python
case "Rainbow":
    return Enemy(ZigZagMovement(), "../images/rainbow_car.png", "Rainbow")
```

Este enemigo es especial: no daña, ¡suma una vida!

---

### 2. Generar RainbowCars en el juego

En `refreshLives()` dentro de `game.py`:

```python
if frame_count % 1200 == 0:
    live = EnemyFactory.create_enemy("Rainbow")
    livesGroup.add(live)
```

Esto lo genera cada 20 segundos (si jugás a 60 FPS).

---

### 3. Detectar colisiones con RainbowCar

En `runGame()`:

```python
RainbowCar_Crash = self.catchCollisions(playerSprite, livesGroup)
if RainbowCar_Crash and Lives < 3:
    Lives += 1
    playerSprite.updateHealth(Lives)
```

Este código incrementa la cantidad de vidas (hasta 3 máximo).

---

### 4. Cambiar visualmente la salud

Ya implementado en `updateHealth()`:

```python
image_path = "../images/" + str(self.color).lower() + "_player_" + str(health) + ".png"
self.image = pygame.image.load(image_path).convert_alpha()
```

---

## ✅ Tareas

- Cambiar la imagen del `RainbowCar` por un ícono de corazón o vida.
- Ajustar el tiempo de aparición para que sea más o menos frecuente.
- Hacer que el `RainbowCar` se mueva más lento que otros enemigos (extra).

---

## 🛠 Archivos utilizados
- `enemy.py`
- `game.py`
- `player.py`

## 🧩 Requiere comprensión de:
- Colisiones entre sprites
- Manejo de contadores y condiciones
- Grupos de Pygame (`sprite.Group`)
