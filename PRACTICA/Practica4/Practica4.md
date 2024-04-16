## Ejercicio 1: 
### Ejercicio 1: a) Tome una de las variables de la línea 3 del siguiente código e indique y defina cuales son sus atributos

```Pascal
    1.¿Procedure Practica4();
    2.var
    3.a,i:integer
    4.p:puntero
    5.Begin
    6.a:=0;
    7.new(p);
    8.p:= ^i
    9.for i:=1 to 9 do
    10.a:=a+i;
    11.end;
    12....
    13.p:= ^a;
    14....
    15.dispose(p);
    16.end;
```

Variable a:

- Nombre: a
- Alcance: Variable local , Estatico
- Tipo: Entero,ligadura estatica
- L-valor:Direccion de memoria
- R-valor:9
- T.V: 3-16


b) Compare los atributos de la variable del punto a) con los atributos de la variable de la línea 4. Que dato contiene esta variable?


Variable p:

- Nombre: p
- Alcance: Variable local , Estatico
- Tipo: Puntero,ligadura estatica
- L-valor:Direccion de memoria
- R-valor:Dinamico l-valor de i (linea 8) , l-valor de a (linea 13), dispose (linea 15)
- T.V: 3-16


## Ejercicio 2:
### a. Indique cuales son las diferentes formas de inicializar una variable en el momento de la declaración de la misma.

En algunos lenguajes existe la inicialización por defecto, donde los enteros se inicalizan en 0, los booleanos en false, los caracteres en blanco, las funciones en void, etc.

En muchos otros lenguajes, la inicialización por defecto no existe y las variables no inicializadas toman valores basura, lo que puede llevar a errores.

### b. Analice en los lenguajes: Java, C, Phyton y Ruby las diferentes formas de inicialización de variables que poseen. Realice un cuadro comparativo de esta característica.

| **Lenguaje** | |
| --- | --- |
| **Java** | - Declaración e inicialización separadas: `int num; num = 10;`<br>- Inicialización por defecto: `int num;` (inicializada a 0 automáticamente) |
| **C** | - Declaración e inicialización en la misma línea: `int num = 10;`<br>- Declaración e inicialización separadas: `int num; num = 10;`<br>- Las variables globales y estáticas se inicializan por defecto a 0 si no se les asigna un valor explícitamente.<br>- Las variables locales no tienen un valor por defecto y su valor inicial es impredecible, a menos que se les asigne un valor explícitamente. |
| **Python** | - Declaración e inicialización en la misma línea: `num = 10`<br>- No es necesario declarar el tipo de variable antes de su inicialización |
| **Ruby** | - Declaración e inicialización en la misma línea: `num = 10`<br>- No es necesario declarar el tipo de variable antes de su inicialización |



## Ejercicio 3: Explique los siguientes conceptos asociados al atributo l-valor de una:

- a. Variable estática.
- b. Variable automática o semiestática.
- c. Variable dinámica.
- d. Variable semidinámica.


El atributo l-valor de una variable hace referencia a su capacidad de ser referenciada o
manipulada mediante una expresión de asignación. En otras palabras, una variable con l-valor puede ser asignada a otra variable o valor.


a. Variable estática.

Una variable estática tiene un ámbito de visibilidad limitado a la función o archivo en el que se declara y su valor se mantiene constante durante toda la ejecución del programa. Es decir, es una variable que existe y se inicializa en tiempo de compilación y su valor persiste en memoria durante toda la ejecución del programa.

Ejemplo en C:

```C

#include <stdio.h>

void static_example() {
 static int num = 0;
 printf("El valor de num es: %d\n", num);
 num++;
}

int main() {
 for (int i = 0; i < 5; i++) {
 static_example();
 }
 return 0;
}

```
En este ejemplo, la variable num es una variable estática dentro de la función static_example().

La salida del programa sería:

- El valor de num es: 0
- El valor de num es: 1
- El valor de num es: 2
- El valor de num es: 3
- El valor de num es: 4

b. Variable automática o semiestática.

Una variable automática o semiestática se declara dentro de un bloque y su ámbito de
visibilidad se limita a ese bloque. Su valor se inicializa al entrar al bloque y se destruye al salir de él. Estas variables también se llaman locales, ya que solo son visibles dentro de la función en la que se declaran.

Ejemplo en Python:

```py

def automatic_example():
    num = 0
    print("El valor de num es: ", num)
    num += 1

for i in range(5):
    automatic_example()

automatic_example().

```
La salida del programa sería:

- El valor de num es: 0
- El valor de num es: 0
- El valor de num es: 0
- El valor de num es: 0
- El valor de num es: 0

c. Variable dinámica.
Una variable dinámica es una variable que se crea y se destruye en tiempo de ejecución. En la
mayoría de los lenguajes de programación, estas variables se crean utilizando funciones o
métodos específicos como malloc() o new. El valor de una variable dinámica puede cambiar a
lo largo de la ejecución del programa.
Ejemplo en Python:

```
def dynamic_example():
 num = input("Ingrese un número: ")
 print("El valor ingresado es:", num)
for i in range(5):
 dynamic_example()

```

En este ejemplo, la variable num es una variable dinámica que se inicializa mediante la entrada
de usuario en cada llamada a la función dynamic_example().
La salida del programa dependerá de lo que ingrese el usuario.
d. Variable semidinámica.
Una variable semidinámica es aquella cuyo tamaño puede cambiar durante la ejecución del
programa, pero solo se puede ajustar su tamaño en ciertos puntos de control predefinidos. Un
ejemplo de una variable semidinámica en ADA podría ser una matriz cuyo tamaño se puede
ajustar en tiempo de ejecución, pero solo en un punto de control específico del programa.
Ejemplo en ADA:

```

with Ada.Text_IO; use Ada.Text_IO;
procedure Ejemplo_Variable_Semidinamica is
 type Matriz is array (Positive range <>, Positive range <>) of Integer;
 -- Definición de una matriz de tipo semidinámico
 Filas, Columnas : Positive := 5; -- Tamaño inicial de la matriz
 M : Matriz (1..Filas, 1..Columnas); -- Inicialización de la matriz
begin
 -- Realizar alguna operación con la matriz inicial
 Put_Line("El tamaño actual de la matriz es " & Positive'Image(Filas) & "x" &
 Positive'Image(Columnas));
 -- En algún punto de control en el programa, ajustar el tamaño de la matriz
 Filas := 8;
 Columnas := 8;
 M := M (1..Filas, 1..Columnas); -- Ajustar el tamaño de la matriz
 -- Realizar alguna operación con la matriz actualizada
 Put_Line("El tamaño actual de la matriz es " & Positive'Image(Filas) & "x"
& Positive'Image(Columnas));
end Ejemplo_Variable_Semidinamica;

```

En este ejemplo, se define una matriz semidinámica llamada Matriz, que se puede ajustar en tiempo de ejecución. 
En la inicialización de la matriz, se define un tamaño inicial de 5 filas y 5 columnas. 
Luego, en un punto de control específico en el programa, se ajusta el tamaño de la matriz a 8 filas y 8 columnas. 
La variable Filas y Columnas se utilizan para controlar el tamaño actual de la matriz, y la sintaxis M := M (1..Filas, 1..Columnas); se utiliza para ajustar el tamaño
de la matriz en ese punto de control. 
Finalmente, se muestra por pantalla el tamaño actual de la matriz antes y después de ajustar su tamaño.



Investigue sobre que tipos de variables respecto de su l-valor hay en los lenguajes C y Ada.

En el lenguaje de programación C, se pueden clasificar las variables según su l-valor de la siguiente manera:


1. Variable estática: son variables que se almacenan en la memoria estática y mantienen
su valor entre llamadas a funciones. Estas variables se declaran con la palabra clave
"static" y se inicializan automáticamente en cero.

2. Variable automática: son variables que se almacenan en la memoria de la pila y se
eliminan automáticamente al salir de su ámbito de definición. Estas variables se
declaran sin la palabra clave "static" y su vida útil está limitada a su función o bloque
de código.

3. Variable dinámica: son variables que se asignan en tiempo de ejecución y se
almacenan en la memoria dinámica. Estas variables se crean utilizando las funciones
"malloc" o "calloc" y se liberan utilizando la función "free". Estas variables tienen una
vida útil que se extiende más allá de la función o bloque de código en el que se crean.


En el lenguaje de programación Ada, las variables se clasifican según su l-valor de la siguiente manera:

1. Variable estática: se definen usando la palabra clave "constant" o "static" y se
mantiene en memoria durante toda la ejecución del programa.

2. Variable automática o semiestática: se definen dentro de un bloque y se eliminan de la
memoria cuando el bloque termina.

3. Variable dinámica: se asignan en tiempo de ejecución usando la palabra clave "new".
Estas variables se mantienen en la memoria hasta que se libera explícitamente usando
la palabra clave "delete".

4. Variable semidinámica: una matriz cuyo tamaño se puede ajustar en tiempo de
ejecución, pero solo en un punto de control específico del programa.




