
# 📘 Clase 6 – Listas y grupos

## 🎯 Objetivos
- Comprender el uso de listas en Python.
- Aplicar métodos comunes como `append()`, `remove()` y `len()`.
- Introducir el uso de `pygame.sprite.Group` para agrupar enemigos y power-ups.
- Detectar colisiones usando `spritecollide`.

---

## 🧠 Contenidos Teóricos

### ¿Qué es una lista?
Una **lista** es una colección ordenada de elementos:

```python
nombres = ["Ana", "Luis", "Marcos"]
print(nombres[0])  # Ana
```

### Métodos útiles:
- `append(x)` → agrega `x` al final
- `remove(x)` → elimina `x`
- `len(lista)` → devuelve el largo

```python
numeros = [1, 2, 3]
numeros.append(4)  # [1, 2, 3, 4]
numeros.remove(2)  # [1, 3, 4]
```

---

## 💻 Actividad práctica

### 1. Crear grupos de enemigos y power-ups

En `game.py`, se crean grupos con:

```python
enemiesGroup = pygame.sprite.Group()
powerUpGroup = pygame.sprite.Group()
```

Y se agregan elementos con `group.add(sprite)`.

### 2. Colisiones entre grupos

Se usan funciones de `pygame.sprite` para detectar si un jugador choca con un enemigo:

```python
collision = pygame.sprite.spritecollide(player, enemiesGroup, True)
if collision:
    print("¡Choque detectado!")
```

El tercer parámetro indica si se elimina el sprite tras colisión (`True` = sí).

### 3. Iterar sobre elementos de un grupo

```python
for enemigo in enemiesGroup:
    enemigo.update(speed)
```

---

## ✅ Tareas

- Ver cuántos enemigos hay en pantalla usando `len(enemiesGroup)`.
- Crear un grupo nuevo de objetos (por ejemplo, monedas o barriles).
- Agregar una colisión que imprima un mensaje al chocar con un power-up.

---

## 🛠 Archivos utilizados
- `game.py`
- `enemy.py`
- `powerup.py`

## 🧩 Requiere comprensión de:
- Listas
- Iteraciones
- Grupos y sprites en `pygame`
