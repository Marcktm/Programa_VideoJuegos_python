
# 📘 Clase 14 – Refactorización y optimización

## 🎯 Objetivos
- Aprender a mejorar el código sin cambiar su funcionalidad.
- Identificar partes repetidas o mal organizadas del proyecto.
- Comentar correctamente el código para facilitar su mantenimiento.
- Aplicar buenas prácticas de programación.

---

## 🧠 Contenidos Teóricos

### ¿Qué es refactorizar?
Refactorizar es **reorganizar y limpiar el código** para que sea más legible, mantenible y eficiente, sin cambiar cómo funciona.

### Buenas prácticas:
- Usar nombres de variables claros.
- Separar código en funciones reutilizables.
- Eliminar código duplicado.
- Comentar lo necesario (ni de más, ni de menos).

---

## 💻 Actividad práctica

### 1. Revisión de `runGame()` en `game.py`

Esta función contiene mucha lógica, por lo que se puede dividir en partes:

```python
def manejar_colisiones():
    ...
def actualizar_efectos():
    ...
```

Separar la lógica mejora la legibilidad.

---

### 2. Comentar cada sección importante

Por ejemplo:

```python
# Verifica colisiones entre jugador y enemigos
Crash = self.catchCollisions(playerSprite, enemiesGroup)
```

Evitar comentarios como:

```python
# Incrementa variable
frame_count += 1  # Esto no aporta contexto
```

---

### 3. Eliminar código duplicado

Buscar fragmentos que se repitan en varias partes y convertirlos en funciones.

---

### 4. Renombrar variables poco descriptivas

Por ejemplo, cambiar `pu` a `power_up`, `plr` a `player`, etc.

---

### 5. Reorganizar los importes y declaraciones

Asegurarse de que todos los `import` estén al comienzo y no se repitan.

---

## ✅ Tareas

- Dividir `runGame()` en al menos 3 funciones auxiliares.
- Agregar un comentario al inicio de cada archivo explicando su propósito.
- Reescribir nombres de variables que no estén claras.
- Hacer `commit` del código limpio a GitHub (opcional si ya usan control de versiones).

---

## 🛠 Archivos a revisar
- `game.py`
- `main.py`
- `enemy.py`
- `player.py`

## 🧩 Requiere comprensión de:
- Estructura general del código
- Funciones
- Legibilidad y mantenimiento de proyectos
