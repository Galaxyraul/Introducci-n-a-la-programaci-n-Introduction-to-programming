Una vez que disponemos de nuestro entorno de desarrollo y compilador, es el momento de comenzar nuestra aventura en el laberinto de C++. Por ello, vamos a comenzar con un clásico de la programación, aunque es más una broma interna.

Nuestro primer programa será el clásico "Hola Mundo".

## Entrada, Salida y Nuestro Primer Programa
En esta sección vamos a aprender tres cosas: cómo mostrar datos por pantalla, cómo introducir datos y el programa con el que todo programador comienza su carrera. Para hacer uso de entrada/salida en C++, es necesario usar la biblioteca `iostream`. Para la entrada, contamos con `cin`, y para la salida, con `cout`.

Nuestro primer programa será el famoso "Hola Mundo", al que le añadiremos nuestro nombre usando un string, un tipo de dato del que hablaremos más adelante.

```cpp
#include <iostream>
#include <string>

int main() {
    std::string nombre;
    std::cout << "Introduce tu nombre:"; // Usamos << para separar los campos que se mostrarán por pantalla cuando tenemos varios
    std::cin >> nombre; // Escribimos la variable donde se guardará el valor
    // Por último, mostramos nuestro mensaje
    std::cout << "Hola mundo, soy el primer programa de: " << nombre;  
    return 0;
}
```

Por último, hablemos del namespace o espacio de nombre, que sirve como identificador de la biblioteca a la que pertenece la función. Para ello, usamos `using namespace std`. El programa quedaría así:

```cpp
#include <iostream>
#include <string>
using namespace std;

int main() {
    string nombre;
    cout << "Introduce tu nombre:"; // Usamos << para separar los campos que se mostrarán por pantalla cuando tenemos varios
    cin >> nombre; // Escribimos la variable donde se guardará el valor
    // Por último, mostramos nuestro mensaje
    cout << "Hola mundo, soy el primer programa de: " << nombre;  
    return 0;
}
```

Bien, ahora que conocemos cómo mostrar por pantalla e introducir valores, prosigamos con nuestro aprendizaje.



## Primitivas y sus operadores
Ahora procederemos a ver todos los tipos de datos de C++ y los mostraremos por pantalla.

<details>
<summary>int</summary>

Este tipo de dato nos permite almacenar valores enteros, tanto positivos como negativos, utilizando 4 bytes para representar los valores.

**Operadores**
- Suma `+`
- Resta `-`
- Multiplicación `*`
- División `/`
- Incremento `++`: Aumenta el valor de la variable en una unidad. Hay dos tipos: preincremento (se realiza primero el incremento y luego la acción) y postincremento (se realiza primero la acción y luego el incremento).
- Decremento `--`: Lo mismo, pero disminuye.
- Auto operador `operador=`: Aplica sobre la variable el operador. Por ejemplo, `x = 10; x += 15;` hará que `x` sea 25. Esto se puede hacer con el resto de operadores.
- Módulo `%`: Si bien todos estamos familiarizados con las operaciones anteriores, la operación módulo puede resultar rara. Sin embargo, es una operación con la que estamos familiarizados, ya que no es más que el resto de una división. Por ejemplo, `3 % 2 = 1`.

</details>

<details>
<summary>long</summary>
Es igual que el anterior, solo que cuenta con 8 bytes de representación (solo en Linux).
</details>

<details>
<summary>uint</summary>
Es un entero sin signo. A diferencia de los enteros con signo, este no utiliza un bit para determinar si el número es positivo o negativo, aumentando así el valor máximo que se puede almacenar.
</details>

<details>
<summary>float</summary>
Esta primitiva permite almacenar números decimales utilizando 4 bytes de representación.
</details>

<details>
<summary>double</summary>
Es igual que el float, solo que usa 8 bytes de representación.
</details>

Todos los tipos de datos vistos hasta ahora comparten los mismos operadores que `int`, salvo incremento y decremento.

<details>
<summary>bool</summary>

Almacena un valor booleano, es decir, un bit que guarda un 1 si es verdadero y un 0 si es falso. Nos permite hacer uso de las estructuras de control. Los valores que usa son `true` y `false`.

**Operadores**
- Unión `||`: Devuelve verdadero si alguno de los elementos es verdadero y falso si todos son falsos. Por ejemplo, `a || b` devolverá verdadero si `a`, `b`, o ambos son verdaderos.
- Intersección `&&`: Devuelve verdadero si todos los elementos son verdaderos y falso si al menos uno de ellos es falso. Por ejemplo, `a && b` devolverá verdadero si y solo si `a` y `b` son verdaderos.
- Negación `!`: Invierte el valor de verdad de un booleano. Por ejemplo, `!true = false`.
- Igualdad `==`: Devuelve verdadero si ambos valores son iguales.
- Desigualdad `!=`: Devuelve verdadero si ambos valores son distintos.

</details>

<details>
<summary>char</summary>

Permite almacenar un carácter del código ASCII, como pueden ser letras, números o caracteres especiales como `?` o `!`. Internamente, un carácter es un número entero que tiene un valor asociado [ASCII](https://elcodigoascii.com.ar). En este enlace puedes consultar las equivalencias.

```cpp
#include <iostream>
using namespace std;

int main(){
    char caracter1;
    char caracter2;
    // Forma 1 de almacenar
    caracter1 = 'a';
    // Forma 2 de almacenar
    caracter2 = 97;
    // Ambos almacenan lo mismo
    if (caracter1 == caracter2){
        cout << "Ambos caracteres son iguales\n";
    } else {
        cout << "Ambos caracteres no son iguales";
    }
}
```

</details>

<details>
<summary>string</summary>
Los caracteres están muy bien, pero las palabras son un conjunto de estos. Por ello, se vio la necesidad de crear una estructura que almacena conjuntos de caracteres. Una cadena puede estar compuesta de un solo carácter.

**Operadores**
- `length()`: Muestra la longitud de la cadena.
- `at(posicion)`: Muestra el carácter en la posición dada (recuerda, empezamos desde 0).
- `+`/`append()`: Ambos métodos añaden una cadena al final de la cadena.
- `substr(posicion_inicial, longitud)`: Obtiene una subcadena que comienza en la posición inicial y toma tantos caracteres como longitud.
- `find(cadena)`: Devuelve la posición de la primera ocurrencia de la cadena.
- `replace(pos, cont, str)`: Sustituye una cantidad `cont` de caracteres por la cadena `str`.
- `insert(pos, str)`: Introduce la cadena `str` en la posición `pos`.
- `erase(pos)`: Borra todos los caracteres a partir de la posición `pos`. Si no se incluye `pos`, lo borra entero.

Todos estos métodos se invocan de la forma `str.metodo()`.
</details>

## Estructuras de control
Como vimos anteriormente, las estructuras de control nos permiten decidir cómo se ejecutará el programa en base a si se cumplen ciertas condiciones. Veámoslo con algunos ejemplos.

<details>
<summary>if-else</summary>

Tomaremos un número entero y estableceremos un rango. Si se incluye en el rango, mostraremos un mensaje de victoria; si no, uno de derrota.
```cpp
#include <iostream>
using namespace std;

int main(){
    int valor;
    cout << "Introduce el valor entero:"; 
    cin >> valor;
    if (valor > 10){
        cout << "Enhorabuena has ganado";
    } else {
        cout << "Lo siento, has perdido";
    }
    return 0;
}
```

</details>
<details>
<summary>if-else if</summary>

Ahora vamos a expandir un poco el programa para utilizar múltiples condiciones independientes. Para ello, programaremos las operaciones de una calculadora.
```cpp
#include <iostream>
using namespace std;

int main(){
    int valor1, valor2;
    char operador;
    cout << "Introduzca el primer valor de la operación:"; 
    cin >> valor1;
    cout << "Introduzca el segundo valor de la operación:"; 
    cin >> valor2;
    cout << "Introduzca el operador (+, -, *, /):"; 
    cin >> operador;
    if (operador == '+'){
        cout << "Realizando la operación " << operador << " con resultado = " << valor1 + valor2;
    } else if (operador == '-'){
        cout << "Realizando la operación " << operador << " con resultado = " << valor1 - valor2;
    } else if (operador == '*'){
        cout << "Realizando la operación " << operador << " con resultado = " << valor1 * valor2;
    } else if (operador == '/'){
        cout << "Realizando la operación " << operador << " con resultado = " << valor1 / valor2;
    } else {
        cout << "Operador no reconocido";
    }
    return 0;
}
```

</details>

<details>
<summary>switch</summary>

Ahora vamos a mostrar el caso del `switch`. Para ello, realizaremos el mismo ejemplo anterior pero utilizando la estructura `switch`.
```cpp
#include <iostream>
using namespace std;

int main(){
    int valor1, valor2;
    char operador;
    cout << "Introduzca el primer valor de la operación:"; 
    cin >> valor1;
    cout << "Introduzca el segundo valor de la operación:"; 
    cin >> valor2;
    cout << "Introduzca el operador (+, -, *, /):"; 
    cin >> operador;
    switch (operador){
        case '+':
            cout << "Realizando la operación " << operador << " con resultado = " << valor1 + valor2;
            break;
        case '-':
            cout << "Realizando la operación " << operador << " con resultado = " << valor1 - valor2;
            break;
        case '*':
            cout << "Realizando la operación " << operador << " con resultado = " << valor1 * valor2;
            break;
        case '/':
            cout << "Realizando la operación " << operador << " con resultado = " << valor1 / valor2;
            break;
        default:
            cout << "Operador no reconocido";
    }
    return 0;
}
```

</details>

<details>
<summary>Operador ternario</summary>

Por último, hay otra forma de escribir las condiciones para hacer asignaciones o variaciones de valores que es más legible que el típico `if-else`. Este es el operador ternario, que tiene tres partes principales: la condición, el caso verdadero y el caso falso.
```cpp
#include <iostream>
using namespace std;

int main(){
    // Forma tradicional 
    int valor1 = 20;
    int max = 30;
    if (valor1 > max){
        max = valor1;
    }
    cout << max << endl;

    valor1 = 40;
    // Con ternario
    max = (valor1 > max) ? valor1 : max;
    cout << max << endl;
}
```
</details>


## Bucles
Ya hemos visto, mediante la introducción al pseudocódigo, cómo funcionan los bucles y sus distintos tipos. Ahora veremos su implementación en C++.

<details>
<summary>Bucle for</summary>

El bucle `for` es el equivalente al bucle "para", por lo que cuenta con un contador, una condición y un incremento.
Ahora haremos un contador del 1 al 10.
```cpp
#include <iostream>
using namespace std;

int main(){
    for (int i = 1; i <= 10; i++){
        cout << i << endl;
    }
    return 0;
}
```
</details>

<details>
<summary>Bucle while</summary>

El bucle `while` es el equivalente al bucle "mientras". Usaremos el mismo ejemplo.
```cpp
#include <iostream>
using namespace std;

int main(){
    int i = 1;
    while (i <= 10){
        cout << i++ << endl; 
    }
    return 0;
}
```
</details>

<details>
<summary>Bucle do while</summary>

Este bucle tiene una peculiaridad que los otros no tienen: aunque la condición se haya cumplido antes de iniciar el bucle, se ejecutará al menos una vez.
```cpp
#include <iostream>
using namespace std;

int main(){
    for (int i = 11; i <= 10; i++){
        cout << "Ejecutando bucle for" << endl;
    }
    int i = 11;
    do{
        cout << "Ejecutando bucle do while" << endl;
    } while (i <= 10);
}
```
Además de los tipos de bucles, te voy a presentar una directiva que, pese a que no comparto su uso, no puedo negar su utilidad. Esta es la directiva `break`, la cual nos permite terminar la ejecución de un bucle. Usualmente se usa dentro de una sentencia `if`, y por esto digo que no recomiendo su uso ya que se puede utilizar como condición de parada en el bucle sin necesidad de usar `break`.
```cpp
#include <iostream>
using namespace std;

int main(){
    for (int i = 1; i <= 10; i++){
        if (i == 5){
            break; // Termina el bucle cuando i es igual a 5
        }
        cout << i << endl;
    }
    return 0;
}
```
</details>



## Funciones y Procedimientos
Como mencionamos en anexos anteriores, los bucles son útiles solo si queremos ejecutar el mismo código repetidas veces de forma consecutiva. Para superar esta limitación, surgieron las funciones y procedimientos. 

Ambos son bloques de código que cuentan con una cabecera y un cuerpo. La cabecera tiene un nombre mediante el cual se llama y unos parámetros que puede usar de forma local. La diferencia reside en que las funciones devuelven un valor y los procedimientos no.

A continuación, mostraremos un ejemplo de ambos:
```cpp
#include <iostream>
using namespace std;

// Al principio de las funciones se pone el tipo de valor que devuelven
int funcion_suma(int num1, int num2){
    // return indica que ese valor se devolverá
    return num1 + num2;
}
// Void indica que no devuelve nada
void procedimiento_resta(int num1, int num2){
    cout << "El resultado de la resta es: " << num1 - num2 << endl;
}

int main(){
    int num1 = 20;
    int num2 = 30;
    // Ojo, num1 y num2 aquí no tienen por qué ser los mismos en la función ya que no están en su alcance, dependerá del orden en el que se manden. Fíjate en la ejecución.
    cout << "El resultado de la suma es: " << funcion_suma(num1, num2) << endl;
    procedimiento_resta(num2, num1);
    return 0;
}
```


## Vectores
Hemos mencionado en secciones anteriores muy brevemente los vectores. Ahora profundizaremos en ellos.

Un vector es una estructura de datos que consiste en posiciones de memoria consecutivas que almacenan datos del mismo tipo.

En C++ los vectores se crean de la siguiente manera:
```cpp
#include <iostream>
using namespace std;

int main(){
    // Los vectores pueden crearse a partir de un conjunto de datos o iniciarse vacíos
    int vector[] = {1, 2, 3, 4, 5};
    cout << vector << endl;
    /* Como puedes ver, el valor mostrado es del tipo 0x0000000A. Esto se debe a que un vector almacena una dirección de memoria.
    Para poder consultar sus elementos haremos uso de los bucles */
    for(int i = 0; i < 5; i++){
        cout << vector[i] << endl;
    }
    // La segunda forma consiste en declarar el tamaño del vector, dejarlo vacío e ir rellenándolo a lo largo de la ejecución
    int vector2[5];
    for (int i = 0; i < 5; i++){
        vector2[i] = i;
        cout << vector2[i] << endl;
    }
    return 0;
}
```

Un string al final es un vector de `char`, por lo que también podemos acceder a sus elementos mediante `[]`.

Aprovecho también para introducirte el último tipo de bucle ya que no tiene sentido sin conocer los vectores. Es una variación del bucle `for` que va elemento a elemento de un vector sin necesidad de los demás parámetros.

```cpp
#include <iostream>
using namespace std;

int main(){
    int vector[] = {1, 2, 3, 4, 5};
    // El formato es tipo de dato del contenido, un nombre temporal y donde están contenidos los objetos
    for (int num : vector){
        cout << num << endl;
    }
    return 0;
}
```



## Structs
Ya hemos hablado al principio de esta introducción sobre los tipos de datos o primitivas, y un struct no es otra cosa más que un tipo de dato que definimos nosotros manualmente. Se compone de variables y funciones.

A continuación, crearemos el struct `usuario` para demostrar su uso:

```cpp
#include <iostream>
using namespace std;

struct usuario {
    string nombre = "";
    int edad;

    void saludar() {
        cout << "Hola, soy " << nombre << endl;
    }
};

int main() {
    usuario raul;
    raul.nombre = "Raúl";
    // Para acceder a los métodos y variables de un elemento, usamos el punto, salvo que sea un puntero, en cuyo caso usamos ->
    raul.saludar();
    return 0;
}
```


## Punteros
Antes de terminar, me gustaría introducirte a tu mejor amigo y peor pesadilla en C++: el puntero. Un puntero no es más que un tipo de dato que almacena direcciones de memoria. A continuación, te mostraré cómo funcionan:

```cpp
#include <iostream>
using namespace std;

int main() {
    // Para indicar que almacenamos un puntero, usamos *
    // nullptr es un valor que indica que no apunta a nada, también se puede representar con 0
    int *num = nullptr;
    int num2 = 20;

    // Para obtener la dirección de memoria de num2, usamos el operador &
    cout << "Dirección de memoria de num2: " << &num2 << endl;

    // Ahora vamos a hacer que el puntero num apunte a num2
    num = &num2;

    // Mostramos si ambas direcciones son iguales y también el contenido al que apunta num
    cout << "Dirección de memoria de num2: " << &num2 << endl;
    cout << "Dirección de memoria a la que apunta num: " << num << endl;

    // Lo útil de los punteros es que nos permite cambiar los valores de la variable a la que apuntan
    num2 = 15;
    cout << "Contenido al que apunta num después de cambiar num2: " << *num << endl;

    *num = 10;
    cout << "Valor de num2 después de cambiar el contenido de num: " << num2 << endl;

    return 0;
}
```

También cabe destacar que un vector es esencialmente un puntero, por lo que al pasarlos como parámetros, podemos definirlos como `int*` o `int[]`. Sin embargo, iterar sobre un vector cuando se pasa como un puntero es un poco más complejo. Aquí te muestro un ejemplo básico:

```cpp
#include <iostream>
using namespace std;

void itera_vector(int *vector, int size) {
    for (int i = 0; i < size; ++i) {
        cout << vector[i] << " ";
    }
    cout << endl;
}

int main() {
    int array[] = {1, 2, 3, 4, 5};
    int size = sizeof(array) / sizeof(array[0]);

    cout << "Iterando sobre el vector desde la función:" << endl;
    itera_vector(array, size);

    return 0;
}
```

En este ejemplo, `itera_vector` recibe un puntero `int*` que apunta al primer elemento del vector y el tamaño del vector. Dentro de la función, se itera sobre el vector utilizando el puntero y el tamaño proporcionados.




## Paso por valor y paso por referencia
Cuando pasamos un parámetro a una función en C++, hay dos formas distintas de hacerlo:

<details>
<summary>Paso por valor</summary>

En este caso, no pasamos directamente la variable como tal, sino una copia de su contenido. Los cambios realizados dentro de la función no afectarán a la variable original.

```cpp
#include <iostream>
using namespace std;

void func(int x) {
    x = x * 2;
    cout << "Dentro de la función: " << x << endl;
}

int main() {
    int num = 5;
    func(num);
    cout << "Fuera de la función: " << num << endl;
    return 0;
}
```

En este ejemplo, la función `func` multiplica el valor por 2, pero el valor de `num` en `main` permanece sin cambios después de llamar a la función.

</details>

<details>
<summary>Paso por referencia</summary>

En este caso, pasamos la dirección de memoria de la variable como argumento a la función. Esto permite que la función pueda modificar directamente el valor de la variable original.

```cpp
#include <iostream>
using namespace std;

void func(int &x) {
    x = x * 2;
    cout << "Dentro de la función: " << x << endl;
}

int main() {
    int num = 5;
    func(num);
    cout << "Fuera de la función: " << num << endl;
    return 0;
}
```

Aquí, al llamar a `func(num)`, la función multiplica `num` por 2. Como `num` se pasó por referencia, los cambios realizados dentro de `func` afectan directamente a `num` en `main`.

</details>

---

Es importante tener en cuenta que los vectores siempre se pasan por referencia implícitamente cuando se usan como argumentos de función. Para evitar modificaciones accidentales dentro de la función, podemos agregar `const` en la declaración de parámetros, lo que indica que la función no modificará el contenido del vector:

```cpp
#include <iostream>
using namespace std;

void func(const int* vector, int tam) {
    for (int i = 0; i < tam; ++i) {
        cout << vector[i] << " ";
    }
    cout << endl;
}

int main() {
    int v[] = {1, 2, 3, 4, 5};
    func(v, 5);
    return 0;
}
```

En este caso, `const int* vector` indica que `vector` es un puntero a un entero constante, es decir, los elementos del vector no se pueden modificar dentro de la función `func`.

## Bibliotecas útiles
### cstdlib
La biblioteca `<cstdlib>` en C++ (o `<stdlib.h>` en C) proporciona funciones para la gestión de memoria dinámica, control del programa y generación de números pseudoaleatorios. Aquí se enfoca principalmente en la función `rand()` para la generación de números aleatorios.

#### `rand()`

La función `rand()` es utilizada para generar números pseudoaleatorios en C y C++. Aquí hay algunos puntos clave sobre `rand()`:

- **Generación de Números Pseudoaleatorios**: `rand()` genera números enteros pseudoaleatorios dentro de un rango predefinido.
  
- **Semilla Inicial**: Para inicializar el generador de números aleatorios, se usa la función `srand()`. Si no se llama a `srand()` explícitamente, `rand()` usa una semilla predeterminada que generalmente se basa en la hora actual del sistema.

- **Limitaciones**: La secuencia de números generada por `rand()` es determinista y repetitiva. Esto significa que si se inicia con la misma semilla, generará la misma secuencia de números cada vez.

- **Rango de Valores**: Por lo general, `rand()` genera números en el rango de 0 a `RAND_MAX`, que es una constante definida en `<cstdlib>` que representa el valor máximo que puede devolver `rand()`.

#### Ejemplo de Uso de `rand()`

```cpp
#include <cstdlib>
#include <ctime>
#include <iostream>

int main() {
    // Semilla basada en el tiempo actual
    srand(time(nullptr));

    // Generar y mostrar 5 números aleatorios entre 0 y 99
    for (int i = 0; i < 5; ++i) {
        int randomNumber = rand() % 100;  // Números entre 0 y 99
        std::cout << randomNumber << std::endl;
    }

    return 0;
}
```

En este ejemplo:
- `srand(time(nullptr))` se utiliza para inicializar `rand()` con una semilla basada en el tiempo actual, asegurando que la secuencia de números generada sea diferente en cada ejecución.
  
- `rand() % 100` se utiliza para obtener números entre 0 y 99. Modificar el número 100 ajusta el rango de los números generados.

### Consideraciones

- **Limitaciones de Aleatoriedad**: `rand()` no produce números aleatorios verdaderos, sino pseudoaleatorios. Es útil para aplicaciones simples que no requieren alta calidad aleatoria, como juegos o simulaciones básicas.
  
- **Alternativas Mejoradas**: Para aplicaciones críticas de seguridad o donde se necesite alta calidad aleatoria, se recomienda usar las facilidades de generación de números aleatorios en la biblioteca `<random>` de C++, que ofrece mayor control y distribuciones más precisas.

En resumen, `rand()` es una función simple pero útil para la generación de números pseudoaleatorios en C y C++, adecuada para aplicaciones donde la precisión y la repetición de la secuencia no sean críticas.
### cmath>

La biblioteca `<cmath>` en C++ proporciona funciones matemáticas estándar que pueden ser utilizadas para realizar operaciones matemáticas avanzadas. Está basada en la biblioteca de funciones matemáticas de C, `<math.h>`, pero adaptada para su uso en C++.

#### Funciones Comunes

Algunas de las funciones más comunes que `<cmath>` proporciona son:

- **Funciones Trigonométricas**: `sin`, `cos`, `tan`, `asin`, `acos`, `atan`, etc.
- **Funciones Exponenciales y Logarítmicas**: `exp`, `log`, `log10`, `pow`, `sqrt`, etc.
- **Funciones de Redondeo**: `ceil`, `floor`, `round`, etc.
- **Funciones de Valor Absoluto**: `abs`, `fabs`, etc.
- **Otras Funciones Matemáticas**: `fmod`, `hypot`, `remainder`, etc.

#### Uso en Ejemplos

```cpp
#include <iostream>
#include <cmath>  // Incluir la biblioteca cmath

using namespace std;

int main() {
    double x = 2.5;
    double y = 1.7;

    // Ejemplo de uso de funciones trigonométricas
    cout << "sin(x) = " << sin(x) << endl;
    cout << "cos(x) = " << cos(x) << endl;
    cout << "atan(y/x) = " << atan(y/x) << endl;

    // Ejemplo de uso de funciones exponenciales y logarítmicas
    cout << "exp(x) = " << exp(x) << endl;
    cout << "log(y) = " << log(y) << endl;

    // Ejemplo de uso de funciones de redondeo
    cout << "ceil(x) = " << ceil(x) << endl;
    cout << "floor(x) = " << floor(x) << endl;

    return 0;
}
```

## Problemas

### Ejercicio 1: Suma de Números Pares

<details>
<summary>Enunciado:</summary>

Escribe un programa que calcule la suma de todos los números pares del 1 al 50 e imprima el resultado.
</details>

<details>
<summary>Solución:</summary>

```cpp
#include <iostream>
using namespace std;

int main() {
    int suma = 0;
    
    for (int i = 2; i <= 50; i += 2) {
        suma += i;
    }
    
    cout << "La suma de los números pares del 1 al 50 es: " << suma << endl;
    
    return 0;
}
```
**Explicación**:
- Inicializamos `suma` en 0 para acumular el resultado.
- Utilizamos un bucle `for` que suma solo números pares del 1 al 50.
- Imprimimos el resultado de la suma al final.

</details>

---

### Ejercicio 2: Calculadora Simple

<details>
<summary>Enunciado:</summary>

Escribe un programa que funcione como una calculadora simple. Debe permitir al usuario ingresar dos números y una operación (+, -, *, /). Luego, debe mostrar el resultado de la operación.
</details>

<details>
<summary>Solución:</summary>

```cpp
#include <iostream>
using namespace std;

int main() {
    float num1, num2;
    char operacion;
    
    cout << "Ingrese el primer número: ";
    cin >> num1;
    cout << "Ingrese el segundo número: ";
    cin >> num2;
    cout << "Ingrese la operación (+, -, *, /): ";
    cin >> operacion;
    
    float resultado;
    
    switch (operacion) {
        case '+':
            resultado = num1 + num2;
            break;
        case '-':
            resultado = num1 - num2;
            break;
        case '*':
            resultado = num1 * num2;
            break;
        case '/':
            if (num2 != 0) {
                resultado = num1 / num2;
            } else {
                cout << "Error: división por cero no permitida." << endl;
                return 1;  // Salir del programa con código de error
            }
            break;
        default:
            cout << "Operación no reconocida." << endl;
            return 1;  // Salir del programa con código de error
    }
    
    cout << "El resultado de " << num1 << " " << operacion << " " << num2 << " es: " << resultado << endl;
    
    return 0;
}
```
**Explicación**:
- Se solicita al usuario que ingrese dos números (`num1` y `num2`) y la operación deseada (`operacion`).
- Se utiliza un `switch` para realizar la operación seleccionada (`+, -, *, /`).
- Se maneja el caso de división por cero para evitar errores.
- Se imprime el resultado de la operación al final.

</details>

---

### Ejercicio 3: Determinar Número Primo

<details>
<summary>Enunciado:</summary>

Escribe un programa que verifique si un número ingresado por el usuario es primo o no. Un número primo es aquel que solo es divisible por sí mismo y por 1.
</details>

<details>
<summary>Solución:</summary>

```cpp
#include <iostream>
using namespace std;

bool esPrimo(int num) {
    if (num <= 1) {
        return false;
    }
    for (int i = 2; i * i <= num; i++) {
        if (num % i == 0) {
            return false;
        }
    }
    return true;
}

int main() {
    int num;
    cout << "Ingrese un número para verificar si es primo: ";
    cin >> num;
    
    if (esPrimo(num)) {
        cout << num << " es un número primo." << endl;
    } else {
        cout << num << " no es un número primo." << endl;
    }
    
    return 0;
}
```
**Explicación**:
- La función `esPrimo` verifica si `num` es primo utilizando un bucle `for` que verifica la divisibilidad hasta la raíz cuadrada de `num`.
- En el `main`, se solicita al usuario ingresar un número y se utiliza la función `esPrimo` para determinar si es primo o no.
</details>

---

### Ejercicio 4: Intercambio de Valores

<details>
<summary>Enunciado:</summary>

Escribe un programa que intercambie los valores de dos variables enteras utilizando solo variables adicionales (sin punteros ni referencias).
</details>

<details>
<summary>Solución:</summary>

```cpp
#include <iostream>
using namespace std;

int main() {
    int num1 = 5, num2 = 10;
    int temp;
    
    cout << "Antes del intercambio:" << endl;
    cout << "num1 = " << num1 << ", num2 = " << num2 << endl;
    
    temp = num1;
    num1 = num2;
    num2 = temp;
    
    cout << "Después del intercambio:" << endl;
    cout << "num1 = " << num1 << ", num2 = " << num2 << endl;
    
    return 0;
}
```
**Explicación**:
- Se inicializan `num1` y `num2`.
- Se utiliza una variable temporal `temp` para intercambiar los valores de `num1` y `num2`.
- Se imprime el resultado antes y después del intercambio.
</details>

---

### Ejercicio 5: Suma de Elementos en un Vector

<details>
<summary>Enunciado:</summary>

Escribe un programa que sume todos los elementos de un vector de enteros. El vector debe ser inicializado con valores dados.
</details>

<details>
<summary>Solución:</summary>

```cpp
#include <iostream>
using namespace std;

int main() {
    int vector[] = {10, 20, 30, 40, 50};
    int tam = 5;
    int suma = 0;
    
    for (int i = 0; i < tam; i++) {
        suma += vector[i];
    }
    
    cout << "La suma de los elementos del vector es: " << suma << endl;
    
    return 0;
}
```
**Explicación**:
- Se inicializa el vector `vector` con valores.
- Se utiliza un bucle `for` para sumar todos los elementos del vector.
- Se imprime la suma total de los elementos del vector.
</details>

---

### Ejercicio 6: Contar Números Positivos y Negativos

<details>
<summary>Enunciado:</summary>

Escribe un programa que cuente cuántos números positivos y cuántos números negativos hay en un vector de enteros inicializado con valores dados.
</details>

<details>
<summary>Solución:</summary>

```cpp
#include <iostream>
using namespace std;

int main() {
    int vector[] = {-1, 2, -3, 4, -5, 6, -7, 8, -9, 10};
    int tam = 10;
    int positivos = 0, negativos = 0;
    
    for (int i = 0; i < tam; i++) {
        if (vector[i] > 0) {
            positivos++;
        } else if (vector[i] < 0) {
            negativos++;
        }
    }
    
    cout << "Número de positivos: " << positivos << endl;
    cout << "Número de negativos: " << negativos << endl;
    
    return 0;
}
```
**Explicación**:
- Se inicializa el vector `vector` con valores.
- Se utiliza un bucle `for` para contar cuántos números son positivos y cuántos son negativos.
- Se imprime el número de positivos y negativos encontrados en el vector.
</details>

---

### Ejercicio 7: Invertir un Número Entero

<details>
<summary>Enunciado:</summary>

Escribe un programa que invierta un número entero ingresado por el usuario (por ejemplo, 12345 invertido sería 54321).
</details>

<details>
<summary>Solución:</summary>

```cpp
#include <iostream>
using namespace std;

int main() {
    int num, original, invertido = 0;
    
    cout << "Ingrese un número entero: ";
    cin >> num;
    
    original = num;
    
    while (num != 0) {
        int digito = num % 10;
        invertido = invertido * 10 + digito;
        num /= 10;
    }
    
    cout << "El número " << original << " invertido es: " << invertido << endl;
    
    return 0;
}
```
**Explicación**:
- Se solicita al usuario ingresar un número entero `num`.
- Se utiliza

 un bucle `while` para invertir el número.
- Se imprime el número original y su versión invertida al final.
</details>

---

### Ejercicio 8: Contar Caracteres en un String

<details>
<summary>Enunciado:</summary>

Escribe un programa que cuente cuántos caracteres tiene un string ingresado por el usuario (sin contar el carácter nulo al final).
</details>

<details>
<summary>Solución:</summary>

```cpp
#include <iostream>
#include <string>
using namespace std;

int main() {
    string texto;
    
    cout << "Ingrese un texto: ";
    getline(cin, texto);
    
    int longitud = texto.length();
    
    cout << "El texto ingresado tiene " << longitud << " caracteres." << endl;
    
    return 0;
}
```
**Explicación**:
- Se utiliza la librería `<string>` para manejar el tipo `string`.
- Se solicita al usuario ingresar un texto con `getline`.
- Se calcula la longitud del texto con el método `length()` y se imprime.
</details>

---

### Ejercicio 9: Generación de Números Aleatorios y Cálculo de Potencia

**Enunciado:**

Escribe un programa en C++ que genere dos números aleatorios entre 1 y 10. Utiliza estos números para calcular la potencia de uno elevado al otro. Muestra los números generados y el resultado de la potencia.

<details>
<summary>Explicación y Solución:</summary>

La biblioteca `<cstdlib>` proporciona la función `rand()` para generar números pseudoaleatorios en C++. La función `rand()` devuelve un número entero aleatorio dentro de un rango. Para obtener números aleatorios diferentes en cada ejecución del programa, es común inicializar el generador de números aleatorios con `srand(time(nullptr))`, utilizando la función `time()` para obtener una semilla única basada en el tiempo actual.

En este ejercicio, `rand() % 10 + 1` genera un número aleatorio entre 1 y 10, y se utiliza la función `pow(base, exponente)` de la biblioteca `<cmath>` para calcular la potencia de un número.

```cpp
#include <iostream>
#include <cstdlib>
#include <ctime>
#include <cmath>

int main() {
    // Inicialización del generador de números aleatorios
    srand(time(nullptr));

    // Generación de dos números aleatorios entre 1 y 10
    int base = rand() % 10 + 1;   // Número aleatorio entre 1 y 10
    int exponente = rand() % 10 + 1;  // Número aleatorio entre 1 y 10

    // Cálculo de la potencia
    double resultado = pow(base, exponente);

    // Mostrar los números generados y el resultado de la potencia
    std::cout << "Número base: " << base << std::endl;
    std::cout << "Exponente: " << exponente << std::endl;
    std::cout << "Resultado de " << base << " elevado a " << exponente << " es " << resultado << std::endl;

    return 0;
}
```

</details>

---

### Ejercicio 10: Cálculo de la Hipotenusa de un Triángulo Rectángulo

**Enunciado:**

Escribe un programa en C++ que solicite al usuario el tamaño de los catetos de un triángulo rectángulo y calcule la longitud de la hipotenusa utilizando la fórmula matemática \( \sqrt{a^2 + b^2} \). Utiliza la función `sqrt()` de la biblioteca `<cmath>` para calcular la raíz cuadrada.

<details>
<summary>Explicación y Solución:</summary>

La biblioteca `<cmath>` proporciona funciones matemáticas como `sqrt()` para calcular raíces cuadradas y `pow()` para calcular potencias. En este ejercicio, se solicita al usuario que ingrese las longitudes de los catetos del triángulo rectángulo, y luego se utiliza la fórmula de Pitágoras para calcular la hipotenusa.

```cpp
#include <iostream>
#include <cmath>

int main() {
    double cateto1, cateto2;

    // Solicitar al usuario los tamaños de los catetos
    std::cout << "Introduce la longitud del primer cateto: ";
    std::cin >> cateto1;

    std::cout << "Introduce la longitud del segundo cateto: ";
    std::cin >> cateto2;

    // Calcular la hipotenusa utilizando la fórmula de Pitágoras
    double hipotenusa = sqrt(pow(cateto1, 2) + pow(cateto2, 2));

    // Mostrar el resultado
    std::cout << "La longitud de la hipotenusa es: " << hipotenusa << std::endl;

    return 0;
}
```

En este código, `pow(cateto1, 2) + pow(cateto2, 2)` calcula la suma de los cuadrados de los catetos, y `sqrt()` se utiliza para calcular la raíz cuadrada de esa suma, que es la longitud de la hipotenusa.

</details>

