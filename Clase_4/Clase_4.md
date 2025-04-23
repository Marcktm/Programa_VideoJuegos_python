
# 📘 Clase 4 – Ciclos y estructuras repetitivas

## 🎯 Objetivos
- Aprender a utilizar bucles `for` y `while` en Python.
- Comprender cómo se repite el movimiento de enemigos en el juego.
- Implementar enemigos estáticos con movimiento descendente.

---

## 🧠 Contenidos Teóricos

### Estructuras repetitivas

#### Bucle `for`
Se usa cuando se conoce cuántas veces se quiere repetir algo:

```python
for i in range(5):
    print("Hola", i)
```

#### Bucle `while`
Se repite mientras una condición sea verdadera:

```python
i = 0
while i < 5:
    print("Hola", i)
    i += 1
```

#### Instrucciones útiles
- `break`: corta el bucle.
- `continue`: salta a la próxima iteración.

---

## 💻 Actividad práctica

### 1. Crear enemigos estáticos (con movimiento hacia abajo)

Desde `game.py`, se usa un bucle para agregar enemigos cada cierto tiempo:

```python
if frame_count % 150 == 0:
    for _ in range(4):
        enemy_type = random.choice(["Yellow", "Blue"])
        enemy = EnemyFactory.create_enemy(enemy_type)
        enemiesGroup.add(enemy)
```

### 2. Movimiento descendente con estrategia fija

En `strategy.py`:

```python
class StillMovement(MovementStrategy):
    def move(self, enemy):
        enemy.posY += enemy.speed
        enemy.rect.center = [enemy.posX, enemy.posY]
```

### 3. Aplicar movimiento con `enemy.update()`

En `enemy.py`:

```python
def update(self, speed):
    self.speed = speed
    self.movement_strategy.move(self)
```

Esto hace que cada enemigo se mueva hacia abajo al actualizarse.

---

## ✅ Tareas

- Ver en pantalla cómo aparecen los enemigos.
- Cambiar la cantidad de enemigos generados por ciclo.
- Probar diferentes valores de velocidad para los enemigos.

---

## 🛠 Archivos utilizados
- `game.py`
- `enemy.py`
- `strategy.py`

## 🧩 Requiere comprensión de:
- Bucles `for` y `while`
- Módulos separados
- Movimiento en coordenadas
