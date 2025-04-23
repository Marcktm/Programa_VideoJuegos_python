
# 📘 Clase 1 – ¿Qué es programar? Primer contacto con Python y Pygame

## 🎯 Objetivos
- Comprender qué es la programación y qué es Python.
- Introducir el entorno de desarrollo y la estructura del videojuego PyRacers.
- Ejecutar el menú de inicio del juego usando el archivo `run.py`.
- Comprender los archivos `main.py` y `screen.py`.

---

## 🧠 Contenidos Teóricos

### ¿Qué es la programación?
La programación es el proceso de crear instrucciones que una computadora puede entender y ejecutar. Permite automatizar tareas y crear aplicaciones como juegos, webs, robots, entre otros.

### ¿Qué es Python?
Python es un lenguaje de programación fácil de leer, usado en ciencia, inteligencia artificial, videojuegos, automatización y más.

### Sintaxis básica:
```python
# Esto es un comentario
print("Hola mundo")  # Imprime un mensaje en pantalla
```

- La indentación en Python es **obligatoria** para definir bloques de código.
- Los comentarios se escriben con `#`.

---

## 💻 Actividad práctica

### 1. Ejecutar el videojuego con `run.py`
Este archivo ejecuta el programa desde consola. Su contenido básico:

```python
import subprocess
import os

main_file_path = os.path.join("src", "main.py")
if os.path.isfile(main_file_path):
    subprocess.run(["python3", main_file_path])
else:
    print("Archivo no encontrado.")
```

### 2. Explorar el archivo `main.py`
Ubica la lógica principal:
- Se inicializa la pantalla con `Screen()`
- Se ejecuta `startScreen()` y luego `runGame()`
- Reinicia el juego tras cada partida

```python
from screen import Screen
from game import Game
...
screen = Screen()
display, clock = screen.startEngine()
...
screen.startScreen()
road_fighter.runGame(...)
```

### 3. Ver archivo `screen.py`
Este archivo gestiona la **pantalla de inicio** y la **pantalla de fin de juego**:
- `startEngine()` configura la ventana.
- `startScreen()` espera que el usuario presione ENTER.
- Se usa `pygame.image.load(...)` para cargar imágenes.

---

## ✅ Tareas

- Ejecutar correctamente el juego desde la terminal.
- Modificar el título de la ventana en `screen.py`.
- Cambiar la imagen de ícono por una propia (opcional).

---

## 🛠 Recursos
- Archivos: `run.py`, `main.py`, `screen.py`
- Librería: `pygame`
