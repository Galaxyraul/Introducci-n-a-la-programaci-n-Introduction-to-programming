# Introducción a la Programación en Python
[Instalación](./Instalacion_IDE.md)
Python es un lenguaje de programación de alto nivel, interpretado y de propósito general. Es conocido por su sintaxis sencilla y legible, lo que lo hace ideal para principiantes, así como para desarrolladores experimentados. En esta introducción, cubriremos los conceptos básicos de Python y proporcionaremos ejercicios prácticos para reforzar el aprendizaje.

## Primitivas y sus Operadores

### Enteros (int)

Este tipo de dato nos permite almacenar valores enteros tanto positivos como negativos.

**Operadores**
- **Suma (`+`)**
- **Resta (`-`)**
- **Multiplicación (`*`)**
- **División (`/`)**
- **División entera (`//`)**
- **Módulo (`%`)**
- **Potencia (`**`)**
- **Incremento (`+=`)**
- **Decremento (`-=`)**

### Flotantes (float)

Esta primitiva permite almacenar números decimales.

**Operadores**
- Mismos que los enteros (`+`, `-`, `*`, `/`, `//`, `%`, `**`)

### Booleanos (bool)

Almacena un valor booleano, es decir, verdadero (`True`) o falso (`False`).

**Operadores**
- **AND (`and`)**
- **OR (`or`)**
- **NOT (`not`)**
- **Igualdad (`==`)**
- **Desigualdad (`!=`)**

### Cadenas (str)

Permite almacenar texto.

**Operadores y métodos comunes**
- **Concatenación (`+`)**
- **Repetición (`*`)**
- **Longitud (`len()`)**
- **Acceso a caracteres (`str[i]`)**
- **Corte de cadenas (`str[start:end]`)**

### Listas (list)

Permiten almacenar múltiples valores de cualquier tipo de dato.

**Operadores y métodos comunes**
- **Acceso a elementos (`list[i]`)**
- **Adición (`append()`)**
- **Inserción (`insert()`)**
- **Eliminación (`remove()`, `pop()`)**
- **Concatenación (`+`)**
- **Repetición (`*`)**

## Estructuras de Control

### if-else

Permiten tomar decisiones en base a condiciones.

```python
valor = int(input("Introduce el valor entero: "))
if valor > 10:
    print("Enhorabuena has ganado")
else:
    print("Lo siento has perdido")
```

### if-elif-else

Para múltiples condiciones independientes.

```python
valor1 = int(input("Introduce el primer valor: "))
valor2 = int(input("Introduce el segundo valor: "))
operador = input("Introduce el operador (+, -, *, /): ")

if operador == '+':
    print(f"Resultado: {valor1 + valor2}")
elif operador == '-':
    print(f"Resultado: {valor1 - valor2}")
elif operador == '*':
    print(f"Resultado: {valor1 * valor2}")
elif operador == '/':
    print(f"Resultado: {valor1 / valor2}")
else:
    print("Operador no reconocido")
```

### for

Para iterar sobre una secuencia.

```python
for i in range(1, 11):
    print(i)
```

### while

Para iterar mientras se cumpla una condición.

```python
i = 1
while i <= 10:
    print(i)
    i += 1
```

## Funciones y Procedimientos

### Funciones

Devuelven un valor y pueden tener parámetros.

```python
def suma(num1, num2):
    return num1 + num2

resultado = suma(10, 20)
print(f"El resultado de la suma es: {resultado}")
```

### Procedimientos

No devuelven un valor.

```python
def resta(num1, num2):
    print(f"El resultado de la resta es: {num1 - num2}")

resta(20, 10)
```

## Vectores (Listas en Python)

### Declaración y Uso

```python
vector = [1, 2, 3, 4, 5]
for num in vector:
    print(num)
```

### Crear lista vacía y agregar elementos

```python
vector2 = []
for i in range(5):
    vector2.append(i)
    print(vector2[i])
```

## Structs (Clases en Python)

### Definición y Uso

```python
class Usuario:
    def __init__(self, nombre, edad):
        self.nombre = nombre
        self.edad = edad

    def saludar(self):
        print(f"Hola, soy {self.nombre}")

raul = Usuario("Raul", 25)
raul.saludar()
```

## Punteros (Referencias en Python)

Python no tiene punteros como en C++, pero las referencias funcionan de manera similar.

### Ejemplo de Referencias

```python
num = 20
num_ref = num
num_ref = 10
print(num)  # Esto seguirá imprimiendo 20
```

### Paso por Valor y Paso por Referencia

En Python, los parámetros se pasan por referencia, pero los tipos inmutables como enteros, cadenas y tuplas se comportan como si se pasaran por valor.

### Paso por Valor

```python
def modificar_valor(valor):
    valor = 10

num = 20
modificar_valor(num)
print(num)  # Esto imprimirá 20
```

### Paso por Referencia

```python
def modificar_lista(lista):
    lista.append(10)

mi_lista = [1, 2, 3]
modificar_lista(mi_lista)
print(mi_lista)  # Esto imprimirá [1, 2, 3, 10]
```

## Biblioteca `math` y `random`

### Biblioteca `math`

La biblioteca `math` proporciona funciones matemáticas básicas y avanzadas.

```python
import math

print(math.sqrt(16))  # Raíz cuadrada
print(math.pi)        # Valor de pi
```

### Biblioteca `random`

La biblioteca `random` permite generar números aleatorios.

```python
import random

print(random.randint(1, 10))  # Número aleatorio entre 1 y 10
print(random.random())        # Número aleatorio entre 0 y 1
```

## Ejercicios Prácticos

### Ejercicio 1: Cálculo de la Hipotenusa

**Enunciado**:
Escribe un programa que calcule la hipotenusa de un triángulo rectángulo dados los catetos.

```python
import math

def calcular_hipotenusa(cateto1, cateto2):
    return math.sqrt(cateto1**2 + cateto2**2)

# Solución
cateto1 = 3
cateto2 = 4
hipotenusa = calcular_hipotenusa(cateto1, cateto2)
print(f"La hipotenusa es: {hipotenusa}")
```

### Ejercicio 2: Números Aleatorios

**Enunciado**:
Escribe un programa que genere 10 números aleatorios entre 1 y 100 y los imprima.

```python
import random

def generar_numeros_aleatorios(cantidad, inicio, fin):
    numeros = []
    for _ in range(cantidad):
        numeros.append(random.randint(inicio, fin))
    return numeros

# Solución
numeros_aleatorios = generar_numeros_aleatorios(10, 1, 100)
print("Números aleatorios generados:", numeros_aleatorios)
```

### Ejercicio 3: Área de un Círculo

**Enunciado**:
Escribe un programa que calcule el área de un círculo dado su radio.

```python
import math

def area_circulo(radio):
    return math.pi * radio**2

# Solución
radio = 5
area = area_circulo(radio)
print(f"El área del círculo es: {area}")
```

### Ejercicio 4: Conversión de Temperaturas

**Enunciado**:
Escribe un programa que convierta una temperatura de grados Celsius a Fahrenheit y viceversa.

```python
def celsius_a_fahrenheit(celsius):
    return celsius * 9/5 + 32

def fahrenheit_a_celsius(fahrenheit):
    return (fahrenheit - 32) * 5/9

# Solución
celsius = 25
fahrenheit = celsius_a_fahrenheit(celsius)
print(f"{celsius}°C es {fahrenheit}°F")

fahrenheit = 77
celsius = fahrenheit_a_celsius(fahrenheit)
print(f"{fahrenheit}°F es {celsius}°C")
```

### Ejercicio 5: Números Primos

**Enunciado**:
Escribe un programa que determine si un número es primo.

```python
def es_primo(numero):
    if numero < 2:
        return False
    for i in range(2, int(math.sqrt(numero)) + 1):
        if numero % i == 0:
            return False
    return True

# Solución
numero = 29
if es_primo(numero):
    print(f"{numero} es primo")
else:
    print(f"{numero} no es primo")
```

### Ejercicio 6: Factorial de un Número

**Enunciado**:
Escribe un programa que calcule el factorial de un número dado.

```python
def factorial(n):
    if n == 0:
        return 1
    else:
        return n

 * factorial(n - 1)

# Solución
numero = 5
print(f"El factorial de {numero} es {factorial(numero)}")
```

### Ejercicio 7: Fibonacci

**Enunciado**:
Escribe un programa que imprima los primeros `n` números de la secuencia de Fibonacci.

```python
def fibonacci(n):
    secuencia = [0, 1]
    while len(secuencia) < n:
        secuencia.append(secuencia[-1] + secuencia[-2])
    return secuencia

# Solución
n = 10
print(f"Los primeros {n} números de la secuencia de Fibonacci son: {fibonacci(n)}")
```

### Ejercicio 8: Ordenar una Lista

**Enunciado**:
Escribe un programa que ordene una lista de números de menor a mayor.

```python
def ordenar_lista(lista):
    return sorted(lista)

# Solución
numeros = [5, 2, 9, 1, 5, 6]
print(f"Lista ordenada: {ordenar_lista(numeros)}")
```

### Ejercicio 9: Cálculo de la Raíz Cuadrada

**Enunciado**:
Escribe un programa que calcule la raíz cuadrada de un número utilizando la biblioteca `math`.

```python
import math

def calcular_raiz_cuadrada(numero):
    return math.sqrt(numero)

# Solución
numero = 16
print(f"La raíz cuadrada de {numero} es {calcular_raiz_cuadrada(numero)}")
```

### Ejercicio 10: Generar un Número Aleatorio

**Enunciado**:
Escribe un programa que genere un número aleatorio entre 1 y 50.

```python
import random

def generar_numero_aleatorio(inicio, fin):
    return random.randint(inicio, fin)

# Solución
print(f"El número aleatorio generado es: {generar_numero_aleatorio(1, 50)}")
```

