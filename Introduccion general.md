# Introducción general a la programación
# Índice
- [Introducción](#introducción)
- [Elementos básicos de la programación](#elementos-básicos-de-la-programación)
- [Primitivas](#primitivas)
- [Primitivas avanzadas](#primitivas-avanzadas)
- [Operadores](#operadores)
- [Estructuras de control](#estructuras-de-control)
- [Bucles](#bucles)
- [Funciones](#funciones)
# Introducción
Para comenzar este mini curso me gustaría contar mis comienzos con la programación.  
Mi primer contacto con esta fue cuando tenía 13 años y acababa de entrar a la secundaria, donde conocí la robótica por medio de Lego y la programación por bloques y cómo con algo tan simple como instrucciones de moverse y detectar se podían conseguir cosas más complejas.  
Desde aquel momento quedé enamorado de la programación y aquí estamos, con 21 años, terminando la carrera de ingeniería informática y escribiendo mi primer curso de introducción a la programación.  
Este curso tiene como objetivo presentar los elementos básicos de la programación además de contar con anexos centrados en lenguajes específicos.  
Por último, destacar que lo importante es que disfrutes de la programación y un consejo: "antes de programar, dibuja y antes de dibujar, piensa".  
# Elementos básicos de la programación  
Un ordenador es muy parecido a un humano, este toma unas órdenes y las realiza, sin embargo, los ordenadores a día de hoy no entienden el lenguaje humano, por ello contamos con lenguajes de programación que nos permiten decirle al ordenador lo que queremos que haga. En un futuro, con el avance del procesamiento del lenguaje natural (PLN), es probable que lleguemos a poder comunicarnos con nuestro lenguaje con el ordenador.  
A continuación, trataremos con los elementos comunes que tienen los lenguajes de programación.  

## Primitivas  
Las primitivas son los elementos más básicos con los que contamos en nuestro lenguaje de programación, son los ladrillos que utilizaremos para construir nuestro programa.  
Los elementos más comunes son:  
El formato es nombre (palabra clave genérica)  
- Enteros (int): Nos permite almacenar números enteros.  
- Flotantes (float): Nos permite almacenar números decimales con precisión simple (se refiere a la forma que el ordenador aproxima el número decimal).  
- Caracteres (char): Son valores hexadecimales que representan un carácter del código [ASCII](https://elcodigoascii.com.ar).  
- Booleanos (bool): Representan la veracidad de un enunciado, puede tomar verdadero o falso.  

## Primitivas avanzadas  
Con el avance de la programación, ciertas primitivas más complejas se han ido creando y, debido a su frecuente uso, han sido incluidas en los lenguajes de programación.  
- Vectores: Son múltiples primitivas consecutivas del mismo tipo, por ejemplo, un vector de enteros de tamaño 4 podría ser [1,2,3,4].  
- Cadena de caracteres (string): Los textos que utilizamos están compuestos por múltiples caracteres, y como no hablamos letra a letra, hacemos uso de un vector de caracteres para representar palabras o textos.  

## Operadores  
Todas las primitivas tienen sus operadores asociados, por ejemplo, los enteros cuentan con suma, resta, división, multiplicación y módulo.  
La implementación y forma de estas primitivas depende en gran parte del lenguaje de programación, aunque algunos elementos que se mantienen entre ellos son, por ejemplo, los operadores aritméticos y el acceso a los elementos de un vector por medio de [posición] (¡cuidado! en programación empezamos a contar desde 0, por lo que para acceder a la primera posición sería [0] no [1]). Por ello, dejaremos el tratamiento de ellas para los anexos detallados.  

## Estructuras de control  
Estas estructuras nos permiten decidir el flujo del programa, ya que en algunos casos queremos que se ejecuten distintas partes dependiendo del caso en el que nos encontremos. Por ejemplo, si tenemos el fuego encendido no tocaremos la sartén por la parte metálica, sin embargo, si está apagado y la sartén fría, lo podemos hacer.  

## Bucles  
En la programación hay una regla de oro: DON'T REPEAT YOURSELF (DRY) y una de las herramientas que nos permite esto son los bucles, estos repiten una secuencia de acciones hasta que se cumplen ciertas condiciones.  

## Funciones  
Siguiendo el mismo principio citado anteriormente, si realizamos una misma acción solo que esta vez la realizamos en diferentes sitios del programa, los bucles ya no nos serán útiles, por ello contamos con las funciones. Estas tienen un nombre mediante el cual pueden ser invocadas para ejecutar el código que contienen.  

Es normal que esta cantidad de información tan repentina te haya impactado, pero no te desanimes. En la siguiente sección veremos muy pocos conceptos nuevos y profundizaremos en los que hemos adquirido llevándolos a la práctica con el pseudocódigo.  

 

