# Introducción a la Programación en Java

## Conceptos Básicos

### Variables y Tipos de Datos

En Java, las variables son contenedores que almacenan datos. Los tipos de datos especifican qué tipo de valores puede contener una variable.

#### Tipos de Datos Primitivos

1. **int:** Almacena números enteros (sin decimales), como 123 o -456.
   ```java
   int edad = 25;
   ```

2. **double:** Almacena números decimales.
   ```java
   double altura = 1.75;
   ```

3. **char:** Almacena un solo carácter, como 'a' o 'B'.
   ```java
   char inicial = 'A';
   ```

4. **boolean:** Almacena valores de verdad (true o false).
   ```java
   boolean esJavaDivertido = true;
   ```

#### Tipos de Datos Referenciados

1. **String:** Almacena cadenas de texto.
   ```java
   String nombre = "Juan";
   ```

### Operadores

Java utiliza una variedad de operadores para realizar operaciones en variables y valores.

#### Operadores Aritméticos

- Suma: `+`
- Resta: `-`
- Multiplicación: `*`
- División: `/`
- Módulo: `%`

```java
int a = 10;
int b = 5;
int suma = a + b; // 15
int resta = a - b; // 5
int producto = a * b; // 50
int cociente = a / b; // 2
int residuo = a % b; // 0
```

#### Operadores de Comparación

- Igual a: `==`
- No igual a: `!=`
- Mayor que: `>`
- Menor que: `<`
- Mayor o igual que: `>=`
- Menor o igual que: `<=`

```java
int a = 10;
int b = 5;
boolean resultado = a > b; // true
```

#### Operadores Lógicos

- AND lógico: `&&`
- OR lógico: `||`
- NOT lógico: `!`

```java
boolean resultado = (a > b) && (a < 15); // true
```

### Estructuras de Control

#### If-Else

```java
int edad = 20;
if (edad >= 18) {
    System.out.println("Eres mayor de edad.");
} else {
    System.out.println("Eres menor de edad.");
}
```

#### Switch

```java
int dia = 3;
switch (dia) {
    case 1:
        System.out.println("Lunes");
        break;
    case 2:
        System.out.println("Martes");
        break;
    case 3:
        System.out.println("Miércoles");
        break;
    default:
        System.out.println("Día no válido");
}
```

### Bucles

#### For

```java
for (int i = 1; i <= 5; i++) {
    System.out.println(i);
}
```

#### While

```java
int i = 1;
while (i <= 5) {
    System.out.println(i);
    i++;
}
```

#### Do-While

```java
int i = 1;
do {
    System.out.println(i);
    i++;
} while (i <= 5);
```

### Funciones y Procedimientos

En Java, las funciones se llaman métodos. Los métodos pueden devolver un valor o ser void (no devuelven nada).

#### Método que Devuelve un Valor

```java
public class Main {
    public static int sumar(int a, int b) {
        return a + b;
    }

    public static void main(String[] args) {
        int resultado = sumar(5, 3);
        System.out.println("La suma es: " + resultado);
    }
}
```

#### Método void

```java
public class Main {
    public static void imprimirSaludo(String nombre) {
        System.out.println("Hola, " + nombre);
    }

    public static void main(String[] args) {
        imprimirSaludo("Juan");
    }
}
```

### Arreglos (Vectores)

Un arreglo es una colección de elementos del mismo tipo.

```java
public class Main {
    public static void main(String[] args) {
        int[] numeros = {1, 2, 3, 4, 5};
        for (int num : numeros) {
            System.out.println(num);
        }

        int[] otrosNumeros = new int[5];
        for (int i = 0; i < otrosNumeros.length; i++) {
            otrosNumeros[i] = i + 1;
        }

        for (int num : otrosNumeros) {
            System.out.println(num);
        }
    }
}
```

### Clases y Objetos

En Java, una clase es un molde para crear objetos. Los objetos tienen propiedades (variables) y comportamientos (métodos).

```java
public class Usuario {
    String nombre;
    int edad;

    public Usuario(String nombre, int edad) {
        this.nombre = nombre;
        this.edad = edad;
    }

    public void saludar() {
        System.out.println("Hola, soy " + nombre);
    }

    public static void main(String[] args) {
        Usuario usuario1 = new Usuario("Juan", 25);
        usuario1.saludar();
    }
}
```

### Punteros en Java

Java no tiene punteros como C++, pero sí tiene referencias a objetos. Las referencias funcionan de manera similar a los punteros, pero sin la complejidad y peligrosidad de la aritmética de punteros.

```java
public class Main {
    public static void main(String[] args) {
        Usuario usuario1 = new Usuario("Juan", 25);
        Usuario usuario2 = usuario1;

        usuario2.nombre = "Pedro";
        System.out.println(usuario1.nombre); // Imprime "Pedro"
    }
}
```

### Paso por Valor y Referencia

En Java, los tipos primitivos se pasan por valor, mientras que los objetos se pasan por referencia.

#### Paso por Valor

```java
public class Main {
    public static void incrementar(int numero) {
        numero++;
    }

    public static void main(String[] args) {
        int num = 5;
        incrementar(num);
        System.out.println(num); // Imprime 5
    }
}
```

#### Paso por Referencia

```java
public class Usuario {
    String nombre;
    
    public Usuario(String nombre) {
        this.nombre = nombre;
    }

    public static void cambiarNombre(Usuario usuario) {
        usuario.nombre = "Pedro";
    }

    public static void main(String[] args) {
        Usuario usuario1 = new Usuario("Juan");
        cambiarNombre(usuario1);
        System.out.println(usuario1.nombre); // Imprime "Pedro"
    }
}
```

### Biblioteca `Math` y Generación de Números Aleatorios

#### `Math`

La clase `Math` proporciona métodos para realizar operaciones matemáticas, como calcular potencias, raíces cuadradas y trigonometría.

```java
public class Main {
    public static void main(String[] args) {
        double numero = 25.0;
        double raizCuadrada = Math.sqrt(numero);
        System.out.println("La raíz cuadrada de " + numero + " es " + raizCuadrada);
    }
}
```

#### Generación de Números Aleatorios con `Random`

La clase `Random` de `java.util` se utiliza para generar números aleatorios.

```java
import java.util.Random;

public class Main {
    public static void main(String[] args) {
        Random random = new Random();
        int numeroAleatorio = random.nextInt(100); // Número aleatorio entre 0 y 99
        System.out.println("Número aleatorio: " + numeroAleatorio);
    }
}
```

Aquí tienes una serie de ejercicios de Java, adaptados para principiantes:

## Ejercicios de Java

### 1. Suma de Dos Números
<details>
<summary>Enunciado</summary>
Crea un programa que pida al usuario dos números enteros y muestre la suma de ambos.
</details>
<details>
<summary>Solución</summary>

```java
import java.util.Scanner;

public class Suma {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        System.out.print("Introduce el primer número: ");
        int num1 = scanner.nextInt();
        System.out.print("Introduce el segundo número: ");
        int num2 = scanner.nextInt();
        
        int suma = num1 + num2;
        System.out.println("La suma es: " + suma);
    }
}
```
</details>

### 2. Verificación de Mayoría de Edad
<details>
<summary>Enunciado</summary>
Crea un programa que pida la edad del usuario y verifique si es mayor de edad (18 años o más).
</details>
<details>
<summary>Solución</summary>

```java
import java.util.Scanner;

public class MayorDeEdad {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        System.out.print("Introduce tu edad: ");
        int edad = scanner.nextInt();

        if (edad >= 18) {
            System.out.println("Eres mayor de edad.");
        } else {
            System.out.println("Eres menor de edad.");
        }
    }
}
```
</details>

### 3. Tabla de Multiplicar
<details>
<summary>Enunciado</summary>
Escribe un programa que pida un número y muestre su tabla de multiplicar del 1 al 10.
</details>
<details>
<summary>Solución</summary>

```java
import java.util.Scanner;

public class TablaMultiplicar {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        System.out.print("Introduce un número: ");
        int num = scanner.nextInt();

        for (int i = 1; i <= 10; i++) {
            System.out.println(num + " x " + i + " = " + (num * i));
        }
    }
}
```
</details>

### 4. Números Pares del 1 al 20
<details>
<summary>Enunciado</summary>
Crea un programa que muestre todos los números pares del 1 al 20.
</details>
<details>
<summary>Solución</summary>

```java
public class NumerosPares {
    public static void main(String[] args) {
        for (int i = 1; i <= 20; i++) {
            if (i % 2 == 0) {
                System.out.println(i);
            }
        }
    }
}
```
</details>

### 5. Uso de la Clase Math
<details>
<summary>Enunciado</summary>
Escribe un programa que calcule la raíz cuadrada de un número ingresado por el usuario.
</details>
<details>
<summary>Solución</summary>

```java
import java.util.Scanner;

public class RaizCuadrada {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        System.out.print("Introduce un número: ");
        double num = scanner.nextDouble();

        double raiz = Math.sqrt(num);
        System.out.println("La raíz cuadrada de " + num + " es " + raiz);
    }
}
```
</details>

### 6. Generación de Números Aleatorios
<details>
<summary>Enunciado</summary>
Crea un programa que genere y muestre un número aleatorio entre 1 y 100.
</details>
<details>
<summary>Solución</summary>

```java
import java.util.Random;

public class NumeroAleatorio {
    public static void main(String[] args) {
        Random random = new Random();
        int numeroAleatorio = random.nextInt(100) + 1; // Número entre 1 y 100
        System.out.println("Número aleatorio: " + numeroAleatorio);
    }
}
```
</details>

### 7. Uso de Arreglos
<details>
<summary>Enunciado</summary>
Escribe un programa que pida 5 números y los almacene en un arreglo, luego muéstralos en orden inverso.
</details>
<details>
<summary>Solución</summary>

```java
import java.util.Scanner;

public class ArregloInverso {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        int[] numeros = new int[5];

        for (int i = 0; i < 5; i++) {
            System.out.print("Introduce un número: ");
            numeros[i] = scanner.nextInt();
        }

        System.out.println("Números en orden inverso:");
        for (int i = 4; i >= 0; i--) {
            System.out.println(numeros[i]);
        }
    }
}
```
</details>

### 8. Saludo Personalizado
<details>
<summary>Enunciado</summary>
Crea un programa que pida el nombre del usuario y muestre un saludo personalizado.
</details>
<details>
<summary>Solución</summary>

```java
import java.util.Scanner;

public class SaludoPersonalizado {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        System.out.print("Introduce tu nombre: ");
        String nombre = scanner.nextLine();

        System.out.println("Hola, " + nombre + "!");
    }
}
```
</details>