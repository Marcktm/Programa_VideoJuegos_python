
# 📘 Clase 13 – Flujo del juego completo

## 🎯 Objetivos
- Revisar el ciclo principal del juego.
- Controlar correctamente el inicio, pausa, ejecución y reinicio del juego.
- Gestionar la lógica de condiciones de victoria o derrota.

---

## 🧠 Contenidos Teóricos

### ¿Qué es el flujo del juego?
Es la estructura general que define cómo se comporta el juego desde que inicia hasta que termina.

Incluye:
- Pantalla de inicio
- Ciclo de juego activo (`runGame`)
- Pantalla de fin
- Reinicio

---

## 💻 Actividad práctica

### 1. Estructura del ciclo en `main.py`

```python
while True:
    road_fighter.runGame(...)
    screen.endScreen()
    Start()
```

Esto permite que el juego vuelva a comenzar automáticamente después del final.

---

### 2. Variables de control en `runGame()`

```python
gameRunning = False
Lives = 3
Frozen = False
Limitless = False
frame_count = 1
```

Se usan para controlar el estado general del juego.

---

### 3. Inicio del juego con tecla `ENTER`

```python
if playPressed and not gameRunning:
    gameRunning = True
```

Y captura de eventos en `catchControllerEvents()`:

```python
if keys[pygame.K_RETURN]:
    playPressed = True
```

---

### 4. Fin del juego

El juego se detiene si se acaban las vidas:

```python
if not gameRunning or Lives <= 0:
    return False
```

Esto lleva a la pantalla final (`endScreen()`).

---

### 5. Control del tiempo y eventos

El uso de `frame_count` permite medir el tiempo en base a FPS:

```python
frame_count += 1
```

Se usa para:
- Aparecer enemigos
- Generar power-ups
- Controlar duración de efectos

---

## ✅ Tareas

- Probar iniciar y terminar el juego varias veces.
- Cambiar el número inicial de vidas o combustible.
- Agregar un mensaje de "Ganaste" si se supera cierta distancia.

---

## 🛠 Archivos utilizados
- `main.py`
- `game.py`

## 🧩 Requiere comprensión de:
- Ciclos `while`
- Condicionales anidados
- Control de eventos en tiempo real
