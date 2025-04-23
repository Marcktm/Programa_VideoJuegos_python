
# 📘 Clase 7 – Clases y objetos

## 🎯 Objetivos
- Entender qué son las clases y los objetos en Python.
- Analizar la estructura del jugador, enemigos y power-ups como clases.
- Actualizar la salud visual del jugador usando imágenes.

---

## 🧠 Contenidos Teóricos

### ¿Qué es una clase?
Una **clase** es un molde para crear objetos. Define sus atributos (datos) y métodos (acciones).

```python
class Perro:
    def __init__(self, nombre):
        self.nombre = nombre
    
    def ladrar(self):
        print("¡Guau!", self.nombre)
```

### Crear un objeto:
```python
mi_perro = Perro("Firulais")
mi_perro.ladrar()
```

---

## 💻 Actividad práctica

### 1. Analizar `Player`, `Enemy`, `PowerUp`

Estas clases están en sus respectivos archivos (`player.py`, `enemy.py`, `powerup.py`) y heredan de `pygame.sprite.Sprite`.

Ejemplo en `Player`:

```python
class Player(pygame.sprite.Sprite):
    def __init__(self, posX, posY, speed):
        ...
        self.color = "Red"
        self.speed = speed
```

### 2. Actualizar la imagen del jugador según su salud

En `player.py`:

```python
def updateHealth(self, health):
    if health > 0:
        image_path = "../images/" + self.color.lower() + "_player_" + str(health) + ".png"
        self.image = pygame.image.load(image_path).convert_alpha()
```

Cada imagen representa un nivel de vida distinto.

### 3. Acceder a atributos del objeto

```python
jugador.posX = 400
jugador.speed = 5
jugador.update("left")
```

---

## ✅ Tareas

- Cambiar los valores iniciales del jugador (`posX`, `speed`).
- Agregar un atributo nuevo al jugador, como `nombre`.
- Mostrar por consola el número de vidas restantes.

---

## 🛠 Archivos utilizados
- `player.py`
- `enemy.py`
- `powerup.py`

## 🧩 Requiere comprensión de:
- Programación orientada a objetos
- Atributos y métodos
- Representación visual con clases
