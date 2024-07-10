Una vez disponemos de nuestro entorno de desarrollo y compilador es el momento de comenzar nuestra aventura en el laberinto de c++.
Por ello vamos a comenzar con un clásico de la programación aunque es más una inside joke.
Nuestro primer programa será el clásico hola mundo
```cpp
#include <iostream> //Importamos la biblioteca que gestiona las entrada/salida en c++
//En c++ el alcanze de una función esta delimitado por {}
//Main es la función principal del programa, es lo que se ejecutará 
int main(){
    //std es el espacio de nombres donde se incluye la función aquí actua como identificador 
    std::cout << "Hola mundo";
    // El ; indica el final de una directiva
    return 0;
    //Este valor es redundante aunque es una buena práctica incluirlo ya que nos permite comprobar que el programa ha ejecutado correctamente
}
```
Tambien podemos sustituir el uso de std delante incluyendo la directiva `using namespace` el programa quedaría tal que así
```cpp
#include <iostream>
using namespace std;

int main(){
    cout << "Hola mundo";
    return 0;
}
```
Ahora hemos aprendido como mostrar por pantalla valores.

## Primitivas
Ahora procederemos a ver todos los tipos de datos de c++ y los mostraremos por pantalla
```cpp
#include <iostream>
using namespace std;

int main(){
    int entero = 33; // Valor entero que 4 bytes
    long entero_grande = 333333; // Valor entero de 8 bytes
    uint entero_sin_signo = 150; // Valor entero positivo de 4 bytes
    float flotante = 33.33; // Valor decomar de 4 bytes
    double flotante_grande = 33.3333333; //Valor decimal de 8 bytes
    bool boleano = true; // Valor booleano
    char caracter = 'a'; // Caracter ASCII

    cout << "Este valor es un entero "<< entero;
    cout << "Este valor es un long " << entero_grande;
    cout << "Este valor es un float " << flotante;
    cout << "Este valor es un double " << flotante_grande;
    cout << "Este valor es un bool " << boleano; 
    cout << "Este valor es un char " << caracter;
    return 0;
}
```
Como puedes ver las salidas aparecen todas consecutivas haciendo muy dificil saber que es que para separarlos tenemos dos opciones.
Añadir la directiva de fin de linea `endl` o añadir el caracter de escape `\n` ambos producen el mismo resultado


```cpp
#include <iostream>
using namespace std;

int main(){
    int entero = 33;
    long entero_grande = 333333; 
    uint entero_sin_signo = 150;
    float flotante = 33.33;
    double flotante_grande = 33.3333333;
    bool boleano = true;
    char caracter = 'a';

    cout << "Este valor es un entero "<< entero << endl;
    cout << "Este valor es un long " << entero_grande << '\n' ;
    cout << "Este valor es un float " << flotante << endl;
    cout << "Este valor es un double " << flotante_grande << endl;
    cout << "Este valor es un bool " << boleano << endl; 
    cout << "Este valor es un char " << caracter << endl;
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