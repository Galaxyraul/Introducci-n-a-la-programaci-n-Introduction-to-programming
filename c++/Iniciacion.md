Una vez disponemos de nuestro entorno de desarrollo y compilador es el momento de comenzar nuestra aventura en el laberinto de c++.
Por ello vamos a comenzar con un clásico de la programación aunque es más una inside joke.
Nuestro primer programa será el clásico hola mundo
## Entrada Salida y nuestro primer programa
En esta sección vamos ha aprender tres cosas, como mostrar datos por pantalla,como introducir datos y el programa con el que todo programador comienza su carrera.
Para hacer uso de entrada/salida en c++ es necesario usar la biblioteca `istream` de c++, para la entrada contamos con `cin` y para la salida `cout`
Nuestro primer programa será el famoso mundo al que le añadiremos nuestro nombre para lo que usaremos un string dato del que hablaremos más adelante
```cpp
#include <iostream>
#include <string> //En c++ no es necesario es costumbre de c
int main(){
    std::string nombre;
    std::cout << "Introduce tu nombre:"; //Usamos <<  para separar los campos que se mostrarán por pantalla cuando tenemos varios
    std::cin >> nombre; //Escribimos la variable donde se guardará el valor
    //Por último mostramos nuestro mensaje
    std::cout << "Hola mundo soy el primer programa de:" << nombre;  
    return 0;
}
``` 

Por último hablemos del namespace o espacio de nombre que sirve como identificador de la biblioteca a la que pertenece la función para ello usamos `using namespaces` el programa quedaría así.
```cpp
#include <iostream>
#include <string>
using namespace std;

int main(){
    string nombre;
    cout << "Introduce tu nombre:"; //Usamos <<  para separar los campos que se mostrarán por pantalla cuando tenemos varios
    cin >> nombre; //Escribimos la variable donde se guardará el valor
    //Por último mostramos nuestro mensaje
    cout << "Hola mundo soy el primer programa de:" << nombre;  
    return 0;
}
``` 
Bien ahora que conocemos como mostrar por pantalla e introducir valores prosigamos con nuestro aprendizaje

## Primitivas y sus operadores
Ahora procederemos a ver todos los tipos de datos de c++ y los mostraremos por pantalla.

<details>
<summary>int</summary>

Este tipo de dato nos permite almacenar valores enteros tanto positivos como negativos con 4 bytes para representar valores

**Operadores**
- Suma +
- Resta -
- Multiplicación *
- División /
- Incremento ++ : Aumenta el valor de la variable en una unidad, hay dos tipos preincremento (Se realiza primero el incremento y luego la acción) y postincremento (Se realiza primero la acción y luego el incremento)
- Decremento -- : Lo mismo pero disminuye
- Auto operador operador= : Aplica sobre la variable el operador por ejemplo x = 10; x+=15; x sería 25 se puede hacer con el resto de operadores
- Módulo % : Si bien todos estamos familiarizados con las operaciones anteriores, la operación módulo puede resultar rara para vosotros, sin embargo, es una operación con la que estais familiarizados ya que no es más que el resto de una división. Por ejemplo 3 % 2 = 1

</details>

<details>
<summary>long</summary>
Es igual que el anterior solo que cuenta con 8 bytes de representación (solo en linux)
</details>

<details>
<summary>uint</summary>
Es un entero sin signo ya que los datos anteriores utiliza un bit para determinar si el número es positivo o negativo, aumentando así el valor máximo que se puede almacenar.
</details>

<details>
<summary>float</summary>
Esta primitiva permite almacenar números decimales con 4 bytes de representación
</details>

<details>
<summary>double</summary>
Es igual que el float solo que usa 8 bytes de representación
</details>

Todos los tipos de datos vistos hasta ahora comparten los mismos operadores que int salvo incremento y decremento

<details>
<summary>bool</summary>

Almacena un valor booleano es decir un bit que guarda un 1 si es verdaderos y un 0 si es falso, nos permite hacer uso de las estructuras de control, los valores que usa son true y false.

**Operadores**
- Union || : Devuelve verdadero si alguno de los elementos es verdadero y falso si todos son falsos por ejemplo a || b devolverá verdador si a,b o ambos son verdaderos
- Intersección && : Devuelve verdadero si todos los elementos son verdaderos y falso si al menos uno de ellos es falso por ejemplo a && b devolverá verdadero sí y solo sí a y b son verdaderos
- Negación ! : Invierte el valor de verdad de un boleano por ejemplo !true = false 
- Igualdad == : Devuelve verdadero si ambos valores son iguales
- Desigualdad != : Devuelve verdadero si ambos valores son distintos

</details>

<details>
<summary>char</summary>

Permite almacenar un carácter del código ASCII como pueden ser letras números o caracteres especiales como ? o !.
Internamente un carácter es un número entero que tiene un valor asociado [ASCII](https://elcodigoascii.com.ar) en este enlace puedes consultar las equivalencias.

```cpp
#include <iostream>
using namespace std;

int main(){
    char caracter1;
    char caracter2;
    //Forma 1 de almacenar
    caracter1 = 'a';
    //Forma 2 de almacenar
    caracter2 = 97;
    //Ambos almacenan lo mismo
    if (caracter1 == caracter2){
        cout << "Ambos caracteres son iguales\n";
    }else{
        cout << "Ambos caracteres no son iguales";
    }
}
```

</details>

<details>
<summary>string</summary>
Los caracteres están muy bien pero las palabras son un conjunto de estos por ello se vió en la necesidad de crear una estructura que almacena conjuntos de caracteres.
Una cadena puede estar compuesta de un solo caracter

**Operadores**
- length() : Muestra la longitud de la cadena
- at(posicion) : Muestra el caracter en la posición dada (Recuerda empezamos desde 0)
- +/append() : Ambos métodos añaden una cadena al final de la cadena
- substr(posicion_inical,longitud) : Obtiene una subcadena que comienza en la posición inicial y coge tantos caracteres como longitud.
- find(cadena) : Devuelve la posición de la primera ocurrancia de la cadena
- replace(pos,cont,str) : Sustituyes una cantidad cont de caracteres por la cadena str
- insert(pos,str) : introduce la cadena str en la posición pos 
- erase(pos) : Borra todos los caracteres a partir de la posición pos, sino se incluye pos lo borra entero

Todos estos métodos se invocan de la forma str.metodo()
</details>

## Estructuras de control
Como vimos anteteriormente las estructuras de control nos permiten decidir como se ejecutará el programa en base a que se cumplan ciertas condiciones veamoslos con algunos ejemplos.

<details>
<summary >if-else</summary>

Tomaremos un número entero y estableceremos un rango si se incluye en el rango mostraremos un mensaje de victoria sino de derrota.
```cpp
#include <iostream>
using namespace std;

int main(){
    int valor;
    cout << "Introduce el valor entero:"; cin >> valor;
    if (valor > 10){
        cout << "Enhorabuena has ganado";
    }else{
        cout << "Lo siento has perdido";
    }
    return 0;
}
```

</details>
<details>
<summary>if-else if</summary>

Ahora vamos a expandir un poco el programa para utilizar multiples condiciones independientes.Para ello programaremos las operaciones de una calculadora.
```cpp
#include<iostream>
using namespace std;

int main(){
    int valor1,valor2;
    char operador;
    cout << "Introduzca el primer valor de la operación:"; cin >> valor1;
    cout << "Introduzca el segundo valor de la operación:"; cin >> valor2;
    cout << "Introduzca el operador, dispone de +,-,*,/:"; cin >> operador;
    if(operador == '+'){
        cout << "Realizando la operación " << operador << " con resultado = " << valor1+valor2;
    }else if(operador == '-'){
        cout << "Realizando la operación " << operador << " con resultado = " << valor1-valor2;
    }else if(operador == '*'){
        cout << "Realizando la operación " << operador << " con resultado = " << valor1*valor2;
    }else if(operador == '/'){
        cout << "Realizando la operación" << operador << " con resultado = " << valor1/valor2;
    }else{
        cout << "Operador no reconocido";
    }
    return 0;
}
```

</details>

<details>
<summary>Switch</summary>

Ahora vamos a mostrar el caso del switch para ello vamos a realizar el caso anterior pero por medio de la estructura switch.
```cpp
#include<iostream>
using namespace std;

int main(){
    int valor1,valor2;
    char operador;
    cout << "Introduzca el primer valor de la operación:"; cin >> valor1;
    cout << "Introduzca el segundo valor de la operación:"; cin >> valor2;
    cout << "Introduzca el operador, dispone de +,-,*,/:"; cin >> operador;
    switch (operador){
        case '+':
            cout << "Realizando la operación " << operador << " con resultado = " << valor1+valor2;
            break;
        case '-':
            cout << "Realizando la operación " << operador << " con resultado = " << valor1-valor2;
            break;
        case '*':
            cout << "Realizando la operación " << operador << " con resultado = " << valor1*valor2;
            break;
        case '/':
            cout << "Realizando la operación" << operador << " con resultado = " << valor1/valor2;
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

Por último hay otra forma de escribir las condiciones para hacer asignaciones o variaciones de valores que es más legible que el típico if-else, este es el operador ternario que tiene 3 partes principales la condición caso verdadero y caso falso.
```cpp
#include <iostream>
using namespace std;

int main(){
    //forma tradicional 
    int valor1 = 20;
    int max = 30;
    if (valor1 > max){
        max = valor1;
    }
    cout << max << endl;
    valor1 = 40;
    //Con ternario
    max = valor1 > max? valor1:max;
    cout << max << endl;
}
```
</details>

## Bucles
Ya hemos visto mediante la introducción al pseudocódigo como funcionan los bucles y sus distintos tipos, ahora veremos su implementación en c++

<details>
<summary>Bucle for</summary>

Es el equivalente al bucle para por lo que cuenta con contador,condición y aumento.
Ahora haremos un contador del 1 al 10
```cpp
#include <iostream>
using namespace std;

int main(){
    for (int i = 1; i <= 10;i++){
        cout << i << endl;
    }
    return 0;
}
```
</details>

<details>
<summary>Bucle while</summary>

Es el equivalente al bucle mientras, usaremos el mismo ejemplo.
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

Este bucle tiene una peculiaridad que los otros no y es que aunque la condición se haya cumplido antes de iniciar el bucle se ejecutará al menos una vez
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
    }while(i <= 10);
}
```

Además de los tipos de bucles te voy a presentar una directiva que pese a que no comparto su uso no puedo negar su utilidad. Este es la directiva `break` la cual nos permite terminar la ejecución de un bucle, usualmente se usa dentro de una sentencia if y por esto digo que no recomiendo su uso ya que se puede utilizar como condición de parada en el bucle sin necesidad de usar break
</details>

## Funciones y procedimientos
Como ya hablamos en anteriores anexos los bucles son útiles solo si quedemos ejecutar el mismo código repetidas veces de forma consecutiva y para solventar esta limitación surgieron las funciones y procedimientos.
Ambos son trozos de código que cuentan con una cabecera y un cuerpo, la cabecera tiene un nombre con la que se la llama y unos parametros que puede usar de forma local. La diferencia reside en que las funciones devuelven un valor y los procedimientos no.

A continuación mostraremos un ejemplo de ambos
```cpp
#include <iostream>
using namespace std;

//Al principio de las funciones de pone el tipo de valor que devuelve
int funcion_suma (int num1,int num2){
    //return indica que ese valor se devolverá
    return num1 + num2;
}

void procedimiento_resta (int num1,int num2){
    cout << "El resultado de la resta es:"<< num1 - num2 << endl;
}
int main(){
    int num1 = 20;
    int num2 = 30;
    //Ojo num1 y num2 de aquí no tienen por qué ser los mismos en la función ya que no estan en su alcance dependerá del orden en el que se manden fijate en la ejecución
    cout << "El resultado de la suma es:" << funcion_suma(num1,num2) << endl;
    procedimiento_resta(num2,num1);
    return 0;
}
```

## Vectores
Hemos mencionado en secciones anteriores muy brevemente los vectores ahora profundizaremos en ellos.
Un vector es una estructura de datos que consiste en posiciones de memoria consecutivas que almacena datos del mismo tipo.

En c++ los vectores se hacen de la siguiente manera:
```cpp
#include <iostream>
using namespace std;

int main(){
    //Los vectores tienen dos formas de crearse, desde un conjunto de datos o creandolo vacío
    int vector[] = {1,2,3,4,5};
    cout << vector << endl;
    /*Como puedes ver el valor mostrado es del tipo 0x0000000A esto se debe a que un vector almacena una posición de memoria.
    Para poder consultar sus elementos haremos uso de los bucles
    */
    for(int  i = 0; i < 5; i++){
        cout << vector[i] << endl;
    }
    //La segunda forma consiste en declarar el tamaño del vector dejarlo vacío e ir rellenandolo a lo largo de la ejecución
    int vector2[5];
    for (int i = 0; i < 5; i++){
        vector2[i] = i;
        cout << vector2[i] << endl;
    }
    return 0;
}
```

Un string al final es un vector de char por lo que también podemos acceder a sus elementos por medio de []

## Structs

## Punteros