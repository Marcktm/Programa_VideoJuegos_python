
# 📘 Clase 11 – Combustible y aceleración

## 🎯 Objetivos
- Implementar un sistema de combustible en el juego.
- Usar la tecla `Z` para acelerar el vehículo del jugador.
- Asociar el uso del combustible con la distancia recorrida y velocidad.

---

## 🧠 Contenidos Teóricos

### ¿Qué es un sistema de recursos?
Muchos videojuegos implementan recursos como vida, tiempo o combustible para agregar estrategia y desafío.

### Variables comunes:
- `fuel`: nivel de combustible
- `distance`: cuánta distancia se recorrió

---

## 💻 Actividad práctica

### 1. Crear variables `fuel` y `distance`

En `runGame()` dentro de `game.py`:

```python
fuel = 100
distance = 0
```

Estas variables deben actualizarse con el tiempo de juego.

---

### 2. Detectar aceleración con tecla `Z`

En `catchControllerEvents()`:

```python
if keys[pygame.K_z]:
    road.update(20)
    enemiesGroup.update(5)
    ...
    accelerated = True
else:
    enemiesGroup.update(-5)
```

Esto mueve más rápido la ruta y los enemigos.

---

### 3. Consumir combustible y aumentar distancia

Dentro de `runGame()`:

```python
if accelerated:
    distance += 1
    fuel -= 0.05
```

Esto permite recorrer más en menos tiempo, pero se consume combustible.

---

### 4. Mostrar por consola el estado

```python
print("Combustible:", fuel)
print("Distancia:", distance)
```

---

## ✅ Tareas

- Cambiar la tasa de consumo de combustible.
- Crear un sistema de advertencia cuando `fuel < 10`.
- Detener el juego si `fuel <= 0` (desafío extra).

---

## 🛠 Archivos utilizados
- `game.py`

## 🧩 Requiere comprensión de:
- Variables numéricas
- Condicionales
- Eventos de teclado
- Lógica en tiempo real
