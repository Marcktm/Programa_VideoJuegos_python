
# 📘 Clase 2 – Variables, tipos de datos y estructuras básicas

## 🎯 Objetivos
- Entender qué es una variable y cómo se utilizan en Python.
- Conocer los tipos de datos básicos: `int`, `float`, `str`, `bool`.
- Aplicar variables para manipular posiciones y elementos del juego.
- Dibujar el fondo del juego en la pantalla.

---

## 🧠 Contenidos Teóricos

### ¿Qué es una variable?
Una **variable** es un espacio de memoria donde se guarda un dato. En Python, se crean así:

```python
vida = 3
nombre = "Jugador1"
velocidad = 5.5
es_activo = True
```

### Tipos de datos más comunes:
- `int` → números enteros: `10`, `-3`
- `float` → números con decimales: `4.5`, `-2.0`
- `str` → texto: `"Hola"`, `'Mundo'`
- `bool` → booleanos: `True`, `False`

---

## 💻 Actividad práctica

### 1. Mostrar fondo con `road.py`

La clase `Road` utiliza una variable `self.image` para representar el fondo de la ruta:

```python
self.image = pygame.image.load("../images/road.png").convert()
```

Se dibuja con el método `draw()`:

```python
def draw(self):
    self.display.blit(self.image, (0, self.newSpeed - self.image.get_rect().height))
```

### 2. Aplicar coordenadas

Las coordenadas `(x, y)` se usan para posicionar elementos en pantalla.
Por ejemplo:

```python
self.posX = 400
self.posY = 600
self.rect.center = (self.posX, self.posY)
```

Esto define la posición del jugador o un enemigo.

### 3. Usar variables en el juego

Modificar las posiciones o velocidad del jugador implica usar variables declaradas en `__init__` como:

```python
self.speed = 5
```

---

## ✅ Tareas

- Probar modificar la velocidad del jugador en `player.py`.
- Cambiar la posición inicial del jugador (`posX`, `posY`).
- Reemplazar la imagen del fondo por otra (opcional).

---

## 🛠 Archivos utilizados
- `road.py`
- `screen.py`
- `player.py`

## 🧩 Requiere comprensión de:
- Tipos de datos
- Asignación de variables
- Coordenadas en pantalla
