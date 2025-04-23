
# 📘 Clase 5 – Funciones y parámetros

## 🎯 Objetivos
- Comprender qué son las funciones en Python y por qué son importantes.
- Usar funciones con parámetros y valores de retorno.
- Implementar enemigos que se muevan en zigzag.
- Modularizar la creación de enemigos en `game.py`.

---

## 🧠 Contenidos Teóricos

### ¿Qué es una función?
Una **función** es un bloque de código que se puede reutilizar. Se define con `def`:

```python
def saludar(nombre):
    print("Hola", nombre)

saludar("Lucía")  # Salida: Hola Lucía
```

### ¿Qué es un parámetro?
Es una variable que se pasa a una función. También puede retornar valores:

```python
def sumar(a, b):
    return a + b

resultado = sumar(3, 5)  # resultado = 8
```

---

## 💻 Actividad práctica

### 1. Crear enemigos zigzag

Se usa la clase `ZigZagMovement` del archivo `strategy.py`:

```python
class ZigZagMovement(MovementStrategy):
    ...
    def move(self, enemy):
        enemy.posY += enemy.speed
        # Movimiento horizontal
```

### 2. Aplicar la estrategia al crear enemigos

En `enemy.py`, la fábrica de enemigos elige el tipo:

```python
class EnemyFactory:
    @staticmethod
    def create_enemy(enemy_type):
        match enemy_type:
            case "Blue":
                return Enemy(ZigZagMovement(), "../images/blue_car.png", "Blue")
```

### 3. Modularizar creación en `game.py`

Desde `refreshEnemies()`:

```python
enemy = EnemyFactory.create_enemy(enemy_type)
enemiesGroup.add(enemy)
```

Esto hace uso de una función para centralizar la lógica de creación.

---

## ✅ Tareas

- Ver en pantalla la diferencia de movimiento entre enemigos.
- Crear una nueva estrategia de movimiento (desafío).
- Cambiar imágenes de enemigos según tipo.

---

## 🛠 Archivos utilizados
- `strategy.py`
- `enemy.py`
- `game.py`

## 🧩 Requiere comprensión de:
- Funciones con parámetros
- Modularidad
- Movimiento alternativo en pantalla
