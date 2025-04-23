
# 📘 Clase 3 – Condicionales y eventos

## 🎯 Objetivos
- Aprender a usar estructuras condicionales `if`, `elif`, `else`.
- Detectar eventos del teclado usando `pygame`.
- Controlar el movimiento del jugador con las flechas izquierda y derecha.

---

## 🧠 Contenidos Teóricos

### Condicionales en Python

Se utilizan para tomar decisiones:

```python
if condicion:
    # código si la condición es verdadera
elif otra_condicion:
    # otro caso
else:
    # si ninguna condición se cumple
```

Ejemplo:

```python
vida = 3
if vida > 0:
    print("El jugador está vivo")
else:
    print("Game Over")
```

### Operadores lógicos y relacionales:
- Relacionales: `==`, `!=`, `<`, `>`, `<=`, `>=`
- Lógicos: `and`, `or`, `not`

---

## 💻 Actividad práctica

### 1. Leer teclas con `pygame.key.get_pressed()`

Este método permite detectar si una tecla está siendo presionada:

```python
keys = pygame.key.get_pressed()
if keys[pygame.K_LEFT]:
    jugador.update("left")
if keys[pygame.K_RIGHT]:
    jugador.update("right")
```

### 2. Código en `player.py`

El método `update()` recibe una dirección y actualiza la posición:

```python
def update(self, direction):
    if direction == "right" and self.posX < ROAD_RIGHT_BORDER:
        self.posX += self.speed
    elif direction == "left" and self.posX > ROAD_LEFT_BORDER:
        self.posX -= self.speed
    self.rect.center = (self.posX, self.posY)
```

Esto evita que el jugador se salga de los límites de la pista.

---

## ✅ Tareas

- Comprobar el funcionamiento de las flechas izquierda y derecha.
- Modificar la velocidad para ver su efecto.
- Agregar impresión por consola que diga “Moviendo a la izquierda” o “derecha”.

---

## 🛠 Archivos utilizados
- `player.py`
- `game.py`
- `main.py`

## 🧩 Requiere comprensión de:
- Condicionales
- Detección de eventos
- Movimiento en coordenadas
