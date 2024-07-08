# Pseudocódigo

En esta sección voy a presentar una de las herramientas más poderosas con las que cuenta un programador. Si tienes algo de experiencia, sabrás que me refiero al pseudocódigo. Este nos permite realizar una primera aproximación a programar sin la necesidad de conocimientos técnicos de ningún tipo de lenguaje, facilitando comunicar nuestras ideas al resto de nuestro equipo y poder revisar el flujo del programa.

Aprovecho para introducirte un concepto que verás a lo largo de todo tu viaje como programador, que es la abstracción. Esta palabreja no quiere decir nada más que simplificar. Eso es lo que permite el pseudocódigo: tomar un problema complejo y analizar el algoritmo de una forma fácil y sencilla por medio de nuestro lenguaje.

## ¿Cómo escribo pseudocódigo?

Todos los lenguajes de programación tienen sus propias normas en temas como nombrar variables, funciones, comentarios, etc., y el pseudocódigo no es menos.

Primero de todo, las palabras claves del lenguaje son aquellas que usamos en nuestro idioma, por lo que ya conoces todas aunque no sabes cuáles son. Hay múltiples formas de escribir pseudocódigo y yo recomiendo escribirlo como te resulte más comprensible. Nosotros seguiremos las siguientes convenciones en este capítulo:

- Las primitivas y funciones tendrán su primera letra en mayúscula.
- Las variables irán nombradas en minúscula y acompañadas de su tipo de primitiva (Entero a).
- Para nombrar una función cuyo nombre conste de más de una palabra, usaremos la "snake convention", que consiste en unir las palabras por guiones bajos (Esto_es_una_función).
- Los comentarios vendrán precedidos por el carácter #. Si ocupan varias líneas, comenzarán y terminarán con ##.
- No usaremos caracteres especiales ni tildes ni "ñ" en nuestros programas, ya que pueden causar errores.
- Marcaremos el inicio y fin del programa con INI y FIN.

Una vez vistas estas pequeñas reglas, es el momento de repasar y profundizar en los conceptos anteriores por medio de la práctica con el pseudocódigo.

## Primitivas

Anteriormente vimos que eran los elementos básicos de un programa, ahora vamos a ver sus usos.

- Variables: Una variable es pedirle al ordenador que reserve un espacio de memoria para que guarde un valor que no se perderá durante la ejecución del programa. Este puede ser modificado a lo largo de la ejecución.
  A la hora de su creación, se pueden o bien inicializar o instanciar. Ahora veremos ejemplos de ambos:
  
  ```
  # Estos serán los tipos de primitivas con los que contemos
  
  Int entero
  Float flotante
  Bool boleano
  Char caracter
  
  ## En este caso, las variables creadas han sido instanciadas ya que se han creado pero o no cuentan con valor o el lenguaje les habrá dado un valor por defecto ##
  
  # Ahora inicializaremos una variable para que tome el valor 0
  
  Int entero2 = 0
  
  ## Ahora cambiaremos el valor de entero2 y daremos valores al resto de variables ##
  
  entero = 1
  flotante = 1.0
  boleano = True
  caracter = 'a'
  entero2 = 2
  # Observa como no hemos incluido el nombre del tipo de dato para llamar a la variable
  ```
  
- Constantes: A diferencia de las variables, estas solo pueden ser inicializadas y su valor no puede cambiar durante la ejecución del programa.

  ```
  Float PI = 3.14
  ```

  Durante todo el programa, PI tendrá el valor 3.14. Cuando trabajemos con un lenguaje real, propondré una serie de pruebas para que veas el comportamiento de las constantes.

  En este anexo no trataremos con las primitivas avanzadas; las podrás ver en detalle en los anexos de cada lenguaje.

## Operadores

En esta sección mostraremos el uso de algunos operadores. Es un caso muy sencillo, por ello te propongo que escribas tú el pseudocódigo y luego lo compares con la solución.

<details>
<summary>Problema 1</summary>
Crea dos variables que almacenen dos números, súmalos, almacena el resultado en una tercera variable y muéstralos como se ve en el ejemplo:

```
# Este programa muestra 0 
Int a = 0
Muestra(a)
```

Ahora haz el programa que se pide:

<details>
<summary>Solución</summary>

```
Ini
    # Declaramos las variables
    Int num1 = 3
    Int num2 = 5
    Int resultado = num1 + num2
    Muestra(resultado)
Fin
```

</details>
</details>

<details>
<summary>Extra</summary>
<details>
<summary>Solución</summary>

```
Ini
    # Declaramos las variables
    Int num1 = 3
    Int num2 = 5
    Muestra(num1 + num2)
Fin
```

</details>
</details>

Algunos operadores aritméticos especiales son:
- Incremento: Aumenta el valor almacenado en la variable en una unidad. Se representa de la forma variable++.
- Decremento: Disminuye el valor de la variable en una unidad. Se representa de la forma variable--.
- Auto-operadores: Aplica el operador al valor de la variable y el dado. Por ejemplo, variable += 2 suma 2 al valor de la variable.

## Estructuras de control

Hay ocasiones en las que tenemos que decidir qué curso ha de seguir nuestro programa, y para ello evaluamos una función de verdad que devuelve un booleano que decide el curso a seguir.

Las palabras clave que usaremos para realizar las estructuras de control serán: `Sí`, `Sino`, `Caso`, `Según`.

Primero comenzaremos con las sentencias condicionales con Sí y Sino.

Pongamos el caso de un programa simple: damos un número, si este es mayor que 10, mostraremos "Es mayor que 10"; sino, mostraremos "Es menor o igual que 10":

```
Ini
    Int num = 11
    Si num > 10:
        Muestra("El número es mayor que 10")
    Sino
        Muestra("El número es menor o igual que 10")
    Fin_si
Fin
# El programa mostrará: El número es mayor que 10
```

En este programa hacemos distinción en dos condiciones. Ampliémoslo un poco añadiendo una tercera condición: si el número es igual a 10, muestra "El número es igual a 10".

```
Ini
    Int num = 11
    Si num == 10:
        Muestra("El número es igual a 10")
    Sino Si num > 10:
        Muestra("El número es mayor que 10")
    Sino
        Muestra("El número es menor que 10")
    Fin_si
Fin
# El programa mostrará: El número es mayor que 10
```

Observa que cuando se comparan los valores por medio de una igualdad, usamos dos iguales en vez de uno. Esto es común en la mayoría de lenguajes.

Antes de proseguir, te voy a introducir el concepto de la enumeración. Esta técnica consiste en asignar un número identificativo a cada elemento de un conjunto. Por ejemplo, tomemos los colores rojo, azul y verde. Una enumeración de ellos sería 0, 1, 2, donde 0 es rojo, 1 es azul y 2 es verde.

He explicado la enumeración ya que el siguiente elemento suele usar números como casos, pero es más intuitivo explicarlo con colores.

Imaginemos que tenemos tres colores: rojo, azul y verde. Escogemos uno de ellos y queremos mostrarlo, pero no sabemos cuál se ha escogido. Ir comprobando uno a uno qué color es puede resultar en código poco legible. Por ello, muchos lenguajes incluyen la sentencia Según y sus casos:

```
Ini
    Int color = 1
    Según color:
        Caso 0:
            Muestra("El color es rojo")
            Salir()
        Caso 1:
            Muestra("El color es azul")
            Salir()
        Caso 2:
            Muestra("El color es verde")
            Salir()
        Defecto:
            Muestra("Color no reconocido")
Fin
# El programa mostrará: El color es azul
```

En este código se pueden observar dos peculiaridades: la primera es la presencia de la palabra "defecto", que sirve para que en caso de que el valor no esté entre los valores pensados, muestre un mensaje por defecto. El segundo es la presencia de la palabra "Salir()" después de cada caso. ¿Por qué crees que es?

<details>
<summary>Solución</summary>
Esto se debe a que, aunque coincida la condición, el programa, si no se le indica explícitamente la salida, tratará de evaluar la siguiente condición, desperdiciando tiempo.
</details>

Por último, cabe destacar que por medio de operadores lógicos se puede aumentar la complejidad de la condición. Por ejemplo, que num > 10 y num < 20.

## Bucles

Hay tres tipos principales de bucles que nos permiten realizar un fragmento de código múltiples veces consecutivas.

### Bucle Para

Este bucle necesita de tres cosas: la variable contadora, la condición de parada y

 el desplazamiento. Se quedaría algo tal que así: Para contador = 0; contador < 10; contador++.

En cada vuelta (iteración) del bucle se comprobará si el contador es menor que 10. En caso afirmativo, se aumentará el contador y se ejecutará el fragmento. En caso contrario, saldrá del bucle y continuará la ejecución normal.

<details>
<summary>Ejemplo</summary>

```
# En este programa mostraremos los números del 1 al 10
Ini
 Para Int contador = 1; contador <= 10; contador++:
    Muestra(contador)
Fin
```

</details>

### Bucle Mientras

Este bucle es muy parecido al anterior, solo que solo se usa la condición, permitiendo que no sea solamente numérica. Esta ha de ser creada fuera del bucle.

<details>
<summary>Ejemplo</summary>

```
# En este programa mostraremos los números del 1 al 10
Ini

    Int contador = 1
    Mientras contador <= 10:
        # Cuidado con el orden
        Muestra(contador)
        contador++

Fin
```

</details>

### Bucle Hacer Mientras

Este bucle se diferencia del anterior en que siempre realiza al menos una ejecución, ya que la comprobación de la condición se realiza después de la ejecución del fragmento, no antes.

<details>
<summary>Ejemplo</summary>

```
Ini
    # En este caso, poniendo el contador a 10, el bucle ejecutaría una vez, mientras que en el resto de bucles vistos no.
    Int contador = 10
    Hacer:
        # Cuidado con el orden
        Muestra(contador)
        contador++
    Mientras contador <= 10

Fin
```

</details>

### Bucles anidados

En programación existe una técnica que es la anidación, la cual consiste en meter elementos del mismo tipo dentro el uno del otro.

<details>
<summary>Ejemplo</summary>

```
# Aquí vamos a hacer un contador de unidades y decenas
Ini
    Para decenas = 0; decenas < 10; decenas++:
        Para unidades = 0; unidades < 10; unidades++:
            Muestra(decenas*10 + unidades)
Fin
# El programa mostrará los números del 1 al 9 hasta llegar al 10, donde empezará a mostrar 10, 11...
```

</details>

### Funciones

En el apartado anterior hemos aprendido cómo ejecutar múltiples veces consecutivas el mismo fragmento de código, pero ¿y si queremos que sea en distintas partes del código? Para eso están las funciones.

Las funciones son fragmentos de código contenidos en una cabecera que se compone de nombre y parámetros. El nombre es el que usaremos para utilizar el código en su interior, mientras que los parámetros son las variables que necesita el código de la función para poder ejecutarse. Realmente hay dos tipos: las funciones y los procedimientos. En el primero obtenemos un valor de regreso, mientras que en el segundo no. Para devolver el valor a la función usaremos la palabra clave "Devolver".

También hay que tener en cuenta que los resultados de las funciones se pueden tanto almacenar como anidar dentro de otras funciones.

#### Procedimiento

Vamos a crear un procedimiento el cual suma dos números y los muestra por pantalla:

```
Ini
    Suma(Int num1, Int num2):
        Muestra(num1 + num2)

    # Hacemos la invocación
    Suma(3,2)

Fin
# El resultado será 5
```

Como podemos observar, el valor se muestra y desaparece; no es devuelto ni almacenado en ningún lado.

#### Función

Imaginemos que queremos calcular el área de diferentes figuras geométricas, como lo son el cuadrado, el triángulo y la circunferencia. El programa sería el siguiente:

```
Ini

    Float PI = 3.14

    Area_cuadrado(Float lado):
        Devolver(lado*lado)

    Area_triangulo(Float base, Float altura):
        Devolver(base*altura/2)

    Area_circulo(Float radio):
        Devolver(2*PI*radio*radio)

    Float area_c = Area_cuadrado(2)
    Muestra(area_c)

    Muestra(Area_triangulo(5,10))
    
    Muestra(Area_circulo(3))

Fin
```

Antes de concluir con las funciones, vamos a hablar de un concepto que afecta tanto a estas como a las variables: el alcance. El alcance es en qué partes del código puede una acción hacer efecto o utilizarse una variable.

Veamos el siguiente caso:

```
Ini

    Float PI = 3.14

    Area_circulo(Float radio):
        Devolver(2*PI*radio*radio)

    Muestra(PI)
    Muestra(Area_circulo(1))

Fin

# El programa muestra: 3.14 y 6.28
```

En este caso, PI es una constante global, por lo que su alcance es todo el código y podemos acceder a ella desde dentro de la función Area_circulo así como desde el cuerpo principal.

```
Ini

    Area_circulo(Float radio):
        Float PI = 3.14
        Devolver(2*PI*radio*radio)

    Muestra(PI)
    Muestra(Area_circulo(1))

Fin
# El programa mostrará un error ya que no puede mostrar PI
```

En este caso, hemos declarado PI como una constante local, haciendo que solo exista dentro del alcance de la función Area_circulo.

Espero que esta sección no se haya hecho muy pesada, ahora que conoces de los conceptos básicos de la programación pasaremos a ver distintos lenguajes con los que darás tus primeros pasos en la programación