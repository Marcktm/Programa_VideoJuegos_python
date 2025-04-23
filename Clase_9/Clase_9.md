
# 📘 Clase 9 – Sistema de power-ups

## 🎯 Objetivos
- Entender qué son los power-ups en videojuegos.
- Implementar los power-ups Blue (Frozen) y Pink (Limitless).
- Modificar dinámicamente el comportamiento de enemigos y jugador al recoger un power-up.

---

## 🧠 Contenidos Teóricos

### ¿Qué es un power-up?
Un **power-up** es un objeto que el jugador puede recoger y que le otorga una habilidad temporal o permanente.

Ejemplos comunes:
- Invulnerabilidad
- Velocidad extra
- Congelación de enemigos

---

## 💻 Actividad práctica

### 1. Crear y mostrar power-ups

Desde `powerup.py` y `PowerUpFactory`:

```python
class PowerUpFactory:
    @staticmethod
    def create_powerup(powerup_type):
        match powerup_type:
            case "Blue":
                return PowerUp("../images/blue_truck.png", "Blue")
            case "Pink":
                return PowerUp("../images/pink_truck.png", "Pink")
```

Cada objeto tiene una imagen, posición aleatoria y velocidad.

### 2. Generar power-ups cada ciertos frames

En `game.py`:

```python
def refreshPowerUps(self, frame_count, FreezePU, LimitlessPU):
    if frame_count % 900 == 0:
        power = random.choice(["Blue", "Pink"])
        new_powerup = PowerUpFactory.create_powerup(power)
        ...
```

### 3. Aplicar efecto con `notifyAll()`

Cuando hay colisión:

```python
if FreezePU_Crash:
    Frozen = True
    self.notifyAll("Frozen")

if LimitlessPU_Crash:
    Limitless = True
    self.notifyAll("Limitless")
```

En `enemy.py` o `player.py`, el método `updateSub()` cambia el comportamiento visual y de movimiento.

---

## ✅ Tareas

- Hacer que al recoger el power-up cambie la imagen del jugador o enemigos.
- Probar cambiar la frecuencia de aparición (`frame_count % 900`).
- Agregar sonidos o mensajes visuales al recogerlos (extra).

---

## 🛠 Archivos utilizados
- `powerup.py`
- `game.py`
- `enemy.py`
- `player.py`

## 🧩 Requiere comprensión de:
- Manejo de grupos y colisiones
- Aplicación de patrones (Observer)
- Reacción a eventos dinámicos
