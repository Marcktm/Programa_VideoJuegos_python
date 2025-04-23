
# 📘 Clase 8 – Herencia, modularidad y arquitectura del juego

## 🎯 Objetivos
- Comprender cómo funciona la herencia en Python.
- Analizar la arquitectura del juego usando módulos y clases conectadas.
- Aplicar el patrón Observer (`Publisher` y `Subscriber`) para modificar comportamientos dinámicamente.
- Aplicar power-ups que modifican el entorno del juego.

---

## 🧠 Contenidos Teóricos

### Herencia en Python

Permite que una clase “hija” herede atributos y métodos de una clase “padre”:

```python
class Animal:
    def hablar(self):
        print("Hace un sonido")

class Perro(Animal):
    def hablar(self):
        print("Guau")

mi_perro = Perro()
mi_perro.hablar()  # Guau
```

Se usa `super()` para acceder a la clase padre:

```python
super().__init__()
```

---

### Modularidad en Python

Permite dividir el código en varios archivos o "módulos" para que sea más ordenado y reutilizable.

Ejemplos en PyRacers:
- `screen.py`: gestión de pantalla.
- `game.py`: lógica principal.
- `player.py`, `enemy.py`, `powerup.py`: entidades del juego.

---

### Patrón Observer

Conecta objetos mediante eventos, sin que estén directamente relacionados.

En PyRacers:
- `Publisher` → emite eventos (por ejemplo, aplicar power-up).
- `Subscriber` → escucha eventos y responde.

```python
class Game(Publisher):
    self.subscribe(objeto)
    self.notifyAll("Frozen")
```

---

## 💻 Actividad práctica

### 1. Aplicar `notifyAll()` a enemigos y jugador

Desde `game.py`:

```python
self.notifyAll("Frozen")     # Detiene enemigos
self.notifyAll("Limitless")  # Movimiento rápido
self.notifyAll("Reset")      # Vuelve al estado original
```

### 2. Ver efecto en `enemy.py` y `player.py`

Método `updateSub()`:

```python
def updateSub(self, powerup):
    if powerup == "Frozen":
        self.movement_strategy = StillMovement()
    elif powerup == "Limitless":
        self.movement_strategy = ZigZagMovement()
```

---

## ✅ Tareas

- Comprobar visualmente el efecto de cada power-up.
- Cambiar el comportamiento para que el jugador también se vea afectado.
- Agregar impresión por consola que muestre qué evento fue recibido.

---

## 🛠 Archivos utilizados
- `observerp.py`
- `game.py`
- `player.py`
- `enemy.py`

## 🧩 Requiere comprensión de:
- Herencia de clases
- Separación en módulos
- Diseño basado en eventos (Observer)
