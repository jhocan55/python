# Tutorial Completo de Python: De Básico a Avanzado

> Basado en el contenido del [Curso de Python](https://platzi.com/cursos/python/) y [Curso de Python Avanzado](https://platzi.com/cursos/python-avanzado/) de Platzi, por **Carli Code**.

---

## Tabla de Contenidos

### Parte 1: Python Básico
1. [Fundamentos: Variables y Tipos de Datos](#1-fundamentos-variables-y-tipos-de-datos)
2. [Cadenas de Texto (Strings)](#2-cadenas-de-texto-strings)
3. [Colecciones: Listas](#3-colecciones-listas)
4. [Colecciones: Diccionarios](#4-colecciones-diccionarios)
5. [Comprensiones de Listas](#5-comprensiones-de-listas)
6. [Control de Flujo: if / elif / else](#6-control-de-flujo-if--elif--else)
7. [Bucles: for y while](#7-bucles-for-y-while)
8. [Funciones](#8-funciones)
9. [Funciones Lambda, map y filter](#9-funciones-lambda-map-y-filter)
10. [Recursión](#10-recursión)
11. [Manejo de Excepciones](#11-manejo-de-excepciones)
12. [Programación Orientada a Objetos (POO)](#12-programación-orientada-a-objetos-poo)
13. [Herencia y super()](#13-herencia-y-super)

### Parte 2: Python Avanzado
14. [Decoradores](#14-decoradores)
15. [Concurrencia con Threading](#15-concurrencia-con-threading)
16. [Paralelismo con Multiprocessing](#16-paralelismo-con-multiprocessing)

---

## Requisitos Previos

Antes de comenzar, asegúrate de tener Python instalado:

```bash
# Verificar versión de Python
python --version

# Verificar pip
pip --version
```

Descarga la última versión en [python.org](https://www.python.org/downloads/). Durante la instalación, marca la opción **"Agregar Python al PATH"**.

---

# PARTE 1: PYTHON BÁSICO

---

## 1. Fundamentos: Variables y Tipos de Datos

Python maneja tres tipos de datos numéricos básicos y el tipo booleano.

```python
# Enteros (int)
x = 10
print(type(x))   # <class 'int'>

# Flotantes (float)
y = 5.678
print(type(y))   # <class 'float'>

# Notación científica
z = 1.2E6    # 1,200,000.0
a = 1.2E-6   # 0.0000012

# Operaciones aritméticas
print(x + x)   # 20
print(x + y)   # 15.678
print(y + y)   # 11.356

# Booleanos
is_true = True
is_false = False
print(is_true)         # True
print(type(is_true))   # <class 'bool'>
```

### Operadores Numéricos

| Operador | Descripción       | Ejemplo        |
|----------|-------------------|----------------|
| `+`      | Suma              | `10 + 5 = 15`  |
| `-`      | Resta             | `10 - 5 = 5`   |
| `*`      | Multiplicación    | `10 * 5 = 50`  |
| `/`      | División          | `10 / 3 = 3.33`|
| `//`     | División entera   | `10 // 3 = 3`  |
| `%`      | Módulo (resto)    | `10 % 3 = 1`   |
| `**`     | Potencia          | `2 ** 3 = 8`   |

### Operadores de Comparación

```python
x = 10
y = 5

print(x > y)   # True
print(x < y)   # False
print(x == y)  # False
print(x != y)  # True
print(x >= 10) # True
print(x <= 10) # True
```

### Entrada del usuario

```python
name = input("¿Cuál es tu nombre? ")
age = int(input("¿Cuántos años tienes? "))  # Convertir a entero
print(f"Hola {name}, tienes {age} años")
```

---

## 2. Cadenas de Texto (Strings)

Las cadenas son secuencias de caracteres. Python ofrece muchos métodos para manipularlas.

```python
name = 'CARLA Marcela'
last_name = '   Florida     Roman  '

# Repetición y concatenación
print(5 * name)              # Repite la cadena 5 veces
print(name + ' ' + last_name)  # Concatena

# Longitud
print(len(name))       # 13
print(len(last_name))  # 22 (incluye espacios)

# Métodos de transformación
print(name.lower())        # 'carla marcela'
print(name.upper())        # 'CARLA MARCELA'
print(last_name.strip())   # 'Florida     Roman' (elimina espacios extremos)
```

### Métodos útiles de strings

```python
text = "Hola, mundo Python"

print(text.replace("mundo", "universo"))  # 'Hola, universo Python'
print(text.split(", "))                   # ['Hola', 'mundo Python']
print(text.startswith("Hola"))            # True
print(text.endswith("Python"))            # True
print(text.find("mundo"))                # 6 (posición)
print(text.count("o"))                   # 3
```

### F-strings (formato moderno)

```python
name = "Carla"
age = 29
height = 1.60

# F-string: forma más legible de formatear
print(f"Nombre: {name}, Edad: {age}, Altura: {height:.2f}m")
# Salida: Nombre: Carla, Edad: 29, Altura: 1.60m
```

### Indexación y Slicing

```python
text = "Python"

print(text[0])    # 'P'  - primer elemento
print(text[-1])   # 'n'  - último elemento
print(text[1:4])  # 'yth' - slice [inicio:fin]
print(text[:3])   # 'Pyt' - desde el inicio hasta el índice 3
print(text[3:])   # 'hon' - desde el índice 3 hasta el final
```

---

## 3. Colecciones: Listas

Las listas son colecciones **ordenadas y mutables** que pueden almacenar elementos de cualquier tipo.

```python
# Crear listas
to_do = ["Ir al hotel", "Almorzar", "Visitar museo", "Volver al hotel"]
numbers = [1, 2, 3, 4, "cinco"]  # Tipos mixtos
mix = ["uno", 2, 3.14, True, [1, 2, 3]]  # Lista anidada

print(len(mix))          # 5
print(mix[0])            # 'uno'
print(mix[-1])           # [1, 2, 3]
print(mix[2:-2])         # [3.14]

# Agregar elementos
mix.append(False)        # Agrega al final
mix.insert(1, "nuevo")  # Inserta en posición 1

# Buscar un elemento
print(mix.index(True))   # Retorna el índice del elemento

# Estadísticas en listas numéricas
numbers = [1, 2, 100.01, 90.45, 3, 4, 5]
print("Mayor:", max(numbers))   # 100.01
print("Menor:", min(numbers))   # 1

# Eliminar elementos
del numbers[-1]    # Elimina el último
del numbers[:2]    # Elimina los primeros 2
del numbers        # Elimina toda la lista
```

### Slicing (rebanado)

```python
fruits = ["manzana", "pera", "uva", "naranja", "tomate"]

print(fruits[1:3])   # ['pera', 'uva']
print(fruits[:2])    # ['manzana', 'pera']
print(fruits[2:])    # ['uva', 'naranja', 'tomate']
print(fruits[::2])   # ['manzana', 'uva', 'tomate'] - de 2 en 2
print(fruits[::-1])  # Invierte la lista
```

---

## 4. Colecciones: Diccionarios

Los diccionarios almacenan pares **clave: valor** y son **mutables**.

```python
# Diccionario simple
numbers = {1: "uno", 2: "dos", 3: "tres"}
print(numbers[2])   # 'dos'

# Diccionario de información personal
information = {
    "nombre": "Carla",
    "apellido": "Florida",
    "altura": 1.60,
    "edad": 29
}

print(information)           # Diccionario completo
del information["edad"]      # Eliminar una clave

# Métodos principales
print(information.keys())    # dict_keys(['nombre', 'apellido', 'altura'])
print(information.values())  # dict_values(['Carla', 'Florida', 1.60])
print(information.items())   # Pares clave-valor

# Diccionarios anidados
contacts = {
    "Carla": {"apellido": "Florida", "altura": 1.60, "edad": 29},
    "Diego": {"apellido": "Antezana", "altura": 1.80, "edad": 32}
}
print(contacts["Carla"])           # {'apellido': 'Florida', ...}
print(contacts["Diego"]["altura"]) # 1.80
```

---

## 5. Comprensiones de Listas

Las comprensiones de listas permiten crear listas de forma **concisa y eficiente**.

```python
# Cuadrados del 1 al 10
squares = [x**2 for x in range(1, 11)]
print(squares)  # [1, 4, 9, 16, 25, 36, 49, 64, 81, 100]

# Conversión de Celsius a Fahrenheit
celsius = [0, 10, 20, 30, 40]
fahrenheit = [(temp * 9/5) + 32 for temp in celsius]
print(fahrenheit)  # [32.0, 50.0, 68.0, 86.0, 104.0]

# Filtrar números pares (con condición)
evens = [x for x in range(1, 21) if x % 2 == 0]
print(evens)  # [2, 4, 6, 8, 10, 12, 14, 16, 18, 20]

# Comprensión de diccionario
squares_dict = {x: x**2 for x in range(1, 6)}
print(squares_dict)  # {1: 1, 2: 4, 3: 9, 4: 16, 5: 25}
```

### Matriz transpuesta con comprensión anidada

```python
matrix = [
    [1, 2, 3],
    [4, 5, 6],
    [7, 8, 9]
]

# Con comprensión de lista anidada
transposed = [[row[i] for row in matrix] for i in range(len(matrix[0]))]
print(transposed)  # [[1, 4, 7], [2, 5, 8], [3, 6, 9]]
```

---

## 6. Control de Flujo: if / elif / else

```python
# Ejemplo 1: Verificar mayoría de edad
age = int(input("Ingresa tu edad: "))

if age >= 18:
    print("Eres mayor de edad")
else:
    print("Eres menor de edad")

# Ejemplo 2: Calificaciones
score = 75

if score >= 90:
    print("Excelente - A")
elif score >= 80:
    print("Muy bien - B")
elif score >= 70:
    print("Bien - C")
elif score >= 60:
    print("Suficiente - D")
else:
    print("Reprobado - F")

# Ejemplo 3: Operador ternario
status = "mayor" if age >= 18 else "menor"
print(f"Es {status} de edad")
```

---

## 7. Bucles: for y while

### Bucle `for`

```python
# Iterar sobre una lista
numbers = [1, 2, 3, 4, 5, 6]
for i in numbers:
    print("Aquí i es igual a:", i + 1)

# Iterar con range()
for i in range(3, 10):
    print(i)  # 3, 4, 5, 6, 7, 8, 9

# Iterar y buscar
fruits = ["Manzana", "Pera", "Uva", "Naranja", "Tomate"]
for fruit in fruits:
    print(fruit)
    if fruit == "Naranja":
        print("¡Naranja encontrada!")

# enumerate() - obtener índice y valor
for index, fruit in enumerate(fruits):
    print(f"{index}: {fruit}")
```

### Bucle `while`

```python
# Contador básico
x = 0
while x < 5:
    print(x)
    x += 1

# Con break
x = 0
while x < 5:
    if x == 3:
        break   # Sale del bucle cuando x es 3
    print(x)
    x += 1
```

### Sentencias `break` y `continue`

```python
numbers = [1, 2, 3, 4, 5, 6]

# break: detiene el bucle completamente
for i in numbers:
    if i == 3:
        break
    print("Aquí i es igual a:", i)  # Imprime 1, 2

# continue: salta a la siguiente iteración
for i in numbers:
    if i == 3:
        continue
    print(i)  # Imprime 1, 2, 4, 5, 6 (salta el 3)
```

---

## 8. Funciones

Las funciones permiten **reutilizar código** y organizarlo en bloques lógicos.

```python
# Función básica con parámetro opcional
def greet(name, last_name="No tiene apellido"):
    print("Hola", name, last_name)

# Llamadas a la función
greet("Carli", "Florida")          # Hola Carli Florida
greet("Diego")                      # Hola Diego No tiene apellido
greet(last_name="Florida", name="Carli")  # Argumentos por nombre

# Función con retorno de valor
def add(a, b):
    return a + b

result = add(5, 3)
print(result)  # 8

# Función con múltiples retornos
def min_max(numbers):
    return min(numbers), max(numbers)

minimum, maximum = min_max([3, 1, 4, 1, 5, 9, 2, 6])
print(f"Mínimo: {minimum}, Máximo: {maximum}")

# *args - número variable de argumentos
def sum_all(*args):
    return sum(args)

print(sum_all(1, 2, 3, 4, 5))  # 15

# **kwargs - argumentos con nombre variables
def show_info(**kwargs):
    for key, value in kwargs.items():
        print(f"{key}: {value}")

show_info(nombre="Carla", edad=29, ciudad="Buenos Aires")
```

---

## 9. Funciones Lambda, map y filter

### Lambda

Funciones anónimas de una sola línea: `lambda argumentos: expresión`

```python
# Lambda básica
add = lambda a, b: a + b
print(add(10, 4))       # 14

multiply = lambda a, b: a * b
print(multiply(80, 5))  # 400

# Lambda como argumento de ordenamiento
students = [("Ana", 85), ("Luis", 92), ("Maria", 78)]
students.sort(key=lambda student: student[1], reverse=True)
print(students)  # Ordenado por nota descendente
```

### `map()` - Aplicar función a cada elemento

```python
numbers = range(11)   # 0 a 10

# Cuadrado de cada número
squared_numbers = list(map(lambda x: x**2, numbers))
print("Cuadrados:", squared_numbers)
# [0, 1, 4, 9, 16, 25, 36, 49, 64, 81, 100]
```

### `filter()` - Filtrar elementos

```python
numbers = range(11)

# Solo números pares
even_numbers = list(filter(lambda x: x % 2 == 0, numbers))
print("Pares:", even_numbers)
# [0, 2, 4, 6, 8, 10]
```

---

## 10. Recursión

Una función es **recursiva** cuando se llama a sí misma. Siempre necesita un **caso base** para detenerse.

```python
def sum_numbers(n):
    # Caso base: si n es 0, la suma es 0
    if n == 0:
        return 0
    # Caso recursivo: n + suma de (n-1)
    else:
        return n + sum_numbers(n - 1)

result = sum_numbers(5)
print(f"Suma de los primeros 5 números es: {result}")
# sum_numbers(5) = 5 + 4 + 3 + 2 + 1 + 0 = 15

# Factorial recursivo
def factorial(n):
    if n == 0 or n == 1:
        return 1
    return n * factorial(n - 1)

print(factorial(5))  # 120

# Serie de Fibonacci
def fibonacci(n):
    if n <= 1:
        return n
    return fibonacci(n - 1) + fibonacci(n - 2)

print([fibonacci(i) for i in range(10)])
# [0, 1, 1, 2, 3, 5, 8, 13, 21, 34]
```

---

## 11. Manejo de Excepciones

Las excepciones permiten manejar **errores en tiempo de ejecución** sin que el programa se rompa.

```python
# Estructura básica try/except
try:
    divisor = int(input("Ingresa un número divisor: "))
    result = 100 / divisor
    print(result)
except ZeroDivisionError as e:
    print("Error: El divisor no puede ser cero")
    print("Ha ocurrido un error:", e)
except ValueError as e:
    print("Error: Debes introducir un número válido")
    print("Ha ocurrido un error:", e)
```

### Bloque `finally` y excepciones personalizadas

```python
# finally siempre se ejecuta
try:
    file = open("datos.txt", "r")
    content = file.read()
except FileNotFoundError:
    print("El archivo no existe")
finally:
    print("Este bloque siempre se ejecuta")

# Excepción personalizada
class AgeError(Exception):
    pass

def validate_age(age):
    if age < 0 or age > 150:
        raise AgeError(f"Edad inválida: {age}")
    return True

try:
    validate_age(200)
except AgeError as e:
    print(f"Error de validación: {e}")
```

### Jerarquía común de excepciones

```
Exception
├── ValueError      - Valor incorrecto (ej: int("abc"))
├── TypeError       - Tipo incorrecto (ej: "hola" + 5)
├── ZeroDivisionError - División por cero
├── FileNotFoundError - Archivo no encontrado
├── IndexError      - Índice fuera de rango
└── KeyError        - Clave no existe en diccionario
```

---

## 12. Programación Orientada a Objetos (POO)

La POO organiza el código en **clases** (plantillas) y **objetos** (instancias).

### Clase básica

```python
class Person:
    def __init__(self, name, age):
        self.name = name
        self.age = age

    def greet(self):
        print(f"Hola, mi nombre es {self.name} y tengo {self.age}")

# Crear instancias (objetos)
person1 = Person("Ana", 30)
person2 = Person("Luis", 25)

person1.greet()  # Hola, mi nombre es Ana y tengo 30
person2.greet()  # Hola, mi nombre es Luis y tengo 25
```

### Ejemplo práctico: Cuenta Bancaria

```python
class BankAccount:
    def __init__(self, account_holder, balance):
        self.account_holder = account_holder
        self.balance = balance
        self.is_active = True

    def deposit(self, amount):
        if self.is_active:
            self.balance += amount
            print(f"Depósito de {amount}. Saldo actual: {self.balance}")
        else:
            print("No se puede depositar. Cuenta inactiva.")

    def withdraw(self, amount):
        if self.is_active:
            if amount <= self.balance:
                self.balance -= amount
                print(f"Retiro de {amount}. Saldo actual: {self.balance}")
            else:
                print("Saldo insuficiente")

    def deactivate_account(self):
        self.is_active = False
        print("La cuenta ha sido desactivada.")

    def activate_account(self):
        self.is_active = True
        print("La cuenta ha sido activada.")

# Usar la clase
account1 = BankAccount("Ana", 500)
account2 = BankAccount("Luis", 1000)

account1.deposit(200)          # Saldo: 700
account2.deposit(100)          # Saldo: 1100
account1.deactivate_account()  # Desactivar
account1.deposit(50)           # Error: cuenta inactiva
account1.activate_account()    # Reactivar
account1.deposit(50)           # Saldo: 750
```

---

## 13. Herencia y super()

La **herencia** permite crear clases nuevas a partir de clases existentes.

```python
# Clase base (padre)
class Animal:
    def __init__(self, name, species):
        self.name = name
        self.species = species

    def speak(self):
        print(f"{self.name} hace un sonido")

    def __str__(self):
        return f"{self.name} ({self.species})"

# Clases derivadas (hijas)
class Dog(Animal):
    def __init__(self, name, breed):
        super().__init__(name, "Perro")  # Llamar al constructor del padre
        self.breed = breed

    def speak(self):  # Sobreescribir método
        print(f"{self.name} dice: ¡Guau!")

class Cat(Animal):
    def __init__(self, name):
        super().__init__(name, "Gato")

    def speak(self):
        print(f"{self.name} dice: ¡Miau!")

# Polimorfismo: mismo método, diferente comportamiento
animals = [Dog("Rex", "Labrador"), Cat("Luna"), Dog("Buddy", "Poodle")]
for animal in animals:
    animal.speak()  # Cada uno habla a su manera
    print(str(animal))
```

---

# PARTE 2: PYTHON AVANZADO

---

## 14. Decoradores

Un decorador es una función que **envuelve a otra función** para modificar o extender su comportamiento, sin cambiar su código.

### Decorador básico

```python
def log_transaction(func):
    def wrapper():
        print('1. Iniciando log de la transacción...')
        func()                              # Ejecuta la función decorada
        print('3. Log terminado.')
    return wrapper

@log_transaction
def process_payment():
    print('2. Procesando pago...')

process_payment()
# Salida:
# 1. Iniciando log de la transacción...
# 2. Procesando pago...
# 3. Log terminado.
```

### Decorador con parámetros

```python
def check_access(func):
    def wrapper(employee):
        # Comprobar si el empleado tiene rol 'admin'
        if employee.get('role') == 'admin':
            return func(employee)
        else:
            print('ACCESO DENEGADO. Solo los administradores pueden acceder.')
    return wrapper

@check_access
def delete_employee(employee):
    print(f"El empleado {employee['name']} ha sido eliminado.")

admin = {'name': 'Carlos', 'role': 'admin'}
employee = {'name': 'Ana', 'role': 'employee'}

delete_employee(admin)     # El empleado Carlos ha sido eliminado.
delete_employee(employee)  # ACCESO DENEGADO.
```

### Decoradores apilados y con `functools.wraps`

```python
import functools
import time

def timer(func):
    """Mide el tiempo de ejecución de una función."""
    @functools.wraps(func)  # Preserva el nombre y docstring original
    def wrapper(*args, **kwargs):
        start = time.time()
        result = func(*args, **kwargs)
        end = time.time()
        print(f"{func.__name__} tardó {end - start:.4f} segundos")
        return result
    return wrapper

def logger(func):
    """Registra llamadas a la función."""
    @functools.wraps(func)
    def wrapper(*args, **kwargs):
        print(f"Llamando a {func.__name__}")
        return func(*args, **kwargs)
    return wrapper

# Apilar decoradores
@timer
@logger
def calculate(n):
    return sum(range(n))

result = calculate(1000000)
print(f"Resultado: {result}")
```

---

## 15. Concurrencia con Threading

El **threading** permite ejecutar múltiples tareas **concurrentemente** en el mismo proceso. Ideal para tareas que esperan I/O (red, archivos).

```python
import threading
import time

# Función que simula el procesamiento de una solicitud
def process_request(request_id):
    print(f'Procesando solicitud {request_id}')
    time.sleep(3)  # Simula trabajo I/O
    print(f'Solicitud {request_id} completada')

threads = []

for i in range(3):
    # Crear nuevo hilo que ejecutará la función
    thread = threading.Thread(target=process_request, args=(i,))
    threads.append(thread)
    thread.start()

# Esperar a que todos los hilos terminen
for thread in threads:
    thread.join()  # Asegura que el programa espere cada hilo

print('Todas las solicitudes completadas')
# Sin threading: 9 segundos (3 solicitudes × 3s)
# Con threading: ~3 segundos (todas en paralelo)
```

### Threading con Lock (evitar condiciones de carrera)

```python
import threading

counter = 0
lock = threading.Lock()

def increment():
    global counter
    for _ in range(100000):
        with lock:  # Solo un hilo a la vez puede modificar counter
            counter += 1

threads = [threading.Thread(target=increment) for _ in range(5)]
for t in threads:
    t.start()
for t in threads:
    t.join()

print(f"Contador final: {counter}")  # Siempre 500000
```

---

## 16. Paralelismo con Multiprocessing

El **multiprocessing** crea procesos separados para aprovechar **múltiples núcleos de CPU**. Ideal para cálculos intensivos.

```python
import multiprocessing

# Función que calcula el cuadrado de un número
def calculate_square(n):
    return n * n

if __name__ == '__main__':
    numbers = [1, 2, 3, 4, 5]

    # Crear un Pool de procesos (usa todos los núcleos disponibles)
    with multiprocessing.Pool() as pool:
        results = pool.map(calculate_square, numbers)

    print(f'Resultados: {results}')  # [1, 4, 9, 16, 25]
```

### Threading vs Multiprocessing

| Característica     | Threading             | Multiprocessing        |
|--------------------|-----------------------|------------------------|
| Procesos           | Un proceso, N hilos   | N procesos             |
| Memoria            | Compartida            | Separada por proceso   |
| Ideal para         | I/O (red, archivos)   | CPU intensivo          |
| GIL de Python      | Limitado por GIL      | Sin restricción de GIL |
| Complejidad        | Menor                 | Mayor                  |

```python
# Ejemplo comparativo: tarea CPU-intensiva
import time
import threading
import multiprocessing

def cpu_task(n):
    """Tarea que usa mucho CPU."""
    return sum(i * i for i in range(n))

# Con multiprocessing es más rápido para tareas CPU-intensivas
if __name__ == '__main__':
    numbers = [10**6] * 4

    # Secuencial
    start = time.time()
    results = [cpu_task(n) for n in numbers]
    print(f"Secuencial: {time.time() - start:.2f}s")

    # Multiprocessing
    start = time.time()
    with multiprocessing.Pool() as pool:
        results = pool.map(cpu_task, numbers)
    print(f"Multiprocessing: {time.time() - start:.2f}s")
```

---

## Proyecto Final: Batalla Naval

Como proyecto integrador, el curso construye un juego de **Batalla Naval** completo que aplica:

- **Clases y POO**: `Board`, `Ship`, `Player`, `Game`
- **Estructuras de control**: bucles para turnos, condicionales para validar tiros
- **Manejo de excepciones**: entradas inválidas del usuario
- **Listas y matrices**: representación del tablero
- **Funciones**: lógica modular del juego

```python
# Estructura básica del proyecto
class Board:
    def __init__(self, size=10):
        self.size = size
        self.grid = [['.'] * size for _ in range(size)]

    def display(self):
        for row in self.grid:
            print(' '.join(row))

class Ship:
    def __init__(self, name, size):
        self.name = name
        self.size = size
        self.hits = 0

    @property
    def is_sunk(self):
        return self.hits >= self.size

class Player:
    def __init__(self, name):
        self.name = name
        self.board = Board()
        self.ships = []

# Ver el archivo Batalla_naval.py para la implementación completa
```

---

## Resumen del Camino de Aprendizaje

```
Nivel Básico:
  variables → cadenas → listas → diccionarios
      ↓
  if/elif/else → for/while
      ↓
  funciones → lambda → excepciones
      ↓
  Clases → herencia → POO

Nivel Avanzado:
  decoradores → threading → multiprocessing
      ↓
  módulos → paquetes → PyPI
      ↓
  asyncio → programación asíncrona
```

---

## Recursos Adicionales

- **Documentación oficial**: [docs.python.org](https://docs.python.org)
- **PEP 8** (guía de estilo): [pep8.org](https://pep8.org)
- **Curso completo**: [Platzi - Python](https://platzi.com/cursos/python/)
- **Curso avanzado**: [Platzi - Python Avanzado](https://platzi.com/cursos/python-avanzado/)

---

*Tutorial generado a partir del código fuente de los repositorios `jhocan55/python` y `jhocan55/python-avanzado`.*
