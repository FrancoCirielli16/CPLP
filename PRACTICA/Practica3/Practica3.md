## Ejercicio 1: 
### ¿Qué define la semántica?

La semántica describe el significado de 
los símbolos, palabras y frases de un 
lenguaje ya sea lenguaje natural o 
lenguaje informático que es 
sintácticamente válido. Para luego poder darle significado a una 
construcción del lenguaje

## Ejercicio 2:

### a. ¿Qué significa compilar un programa?
Hay un programa llamado Compilador 
que realiza la traducción a lenguaje de
máquina. Se traduce/compila antes de ejecución y pasa por todas las instrucciones antes de la ejecución.


### b. Describa brevemente cada uno de los pasos necesarios para compilar un programa.

1) Etapa de Análisis
    - Análisis léxico (Programa Scanner): Consiste en analizar el programa fuente y dividirlo en tokens, identificando palabras clave, identificadores, operadores, etc.
    - Análisis sintáctico (Programa Parser): Verifica que la estructura del programa cumpla con las reglas de la gramática del lenguaje, generando un árbol de análisis sintáctico.
    - Análisis semántico (Programa de Semántica estática): Realiza verificaciones adicionales sobre la coherencia y consistencia del programa, como la declaración correcta de variables y el uso adecuado de tipos de datos.
2) Etapa de Síntesis
    - Optimización del código: Aplica técnicas para mejorar la eficiencia del programa, como la eliminación de código redundante o la reorganización de instrucciones.
    - Generación del código final: Traduce el programa fuente en lenguaje de alto nivel a lenguaje de máquina, generando el código ejecutable.

Resumiendo:
- Análisis léxico (Programa Scanner): Divide el programa en tokens.
- Análisis sintáctico (Programa Parser): Verifica la estructura del programa.
- Análisis semántico (Programa de Semántica estática): Realiza verificaciones adicionales.
- Optimización del código: Mejora la eficiencia del programa.
- Generación del código final: Traduce el programa a lenguaje de máquina.

### c. ¿En qué paso interviene la semántica y cual es su importancia dentro de la compilación?


## Ejercicio 3: 

### Con respecto al punto anterior ¿es lo mismo compilar un programa que interpretarlo? Justifique su respuesta mostrando las diferencias básicas, ventajas y desventajas de cada uno.

No, compilar un programa e interpretarlo no son lo mismo. Ambos son procesos diferentes para ejecutar código, y tienen diferencias significativas en su enfoque y funcionamiento.

## COMPILACION:

La compilación es un proceso en el que un programa escrito en un lenguaje de programación se traduce completamente a un lenguaje de bajo nivel o código máquina específico para la arquitectura de la computadora objetivo. Este proceso es realizado por un compilador, que verifica la sintaxis del código fuente y lo convierte en un archivo ejecutable.

Ventajas de la compilación:

- Eficiencia: El código compilado se ejecuta directamente en la máquina objetivo, lo que generalmente resulta en un rendimiento más rápido que la interpretación.
- Detección de errores temprana: Los errores de sintaxis y semántica se detectan durante la fase de compilación, lo que facilita su corrección antes de la ejecución del programa.
- Portabilidad: Una vez compilado, el programa se puede ejecutar en cualquier máquina que admita el mismo conjunto de instrucciones, siempre y cuando se recompile para esa arquitectura si es necesario.
- Privacidad del código fuente: El código fuente no se distribuye con el programa compilado, lo que ayuda a proteger la propiedad intelectual.

Desventajas de la compilación:

- Proceso de desarrollo más lento: El tiempo necesario para compilar el código puede ser considerable, especialmente para programas grandes.
- Inflexibilidad: Los cambios en el código requieren volver a compilar el programa, lo que puede ser un proceso costoso en términos de tiempo y recursos.
- Dependencia de la arquitectura: Un programa compilado está vinculado a una arquitectura específica, lo que puede limitar su portabilidad sin recompilación.

## INTERPRETACION:

La interpretación implica ejecutar el código fuente línea por línea mediante un programa llamado intérprete, que lee y ejecuta las instrucciones a medida que se encuentran en el código fuente.

Ventajas de la interpretación:

- Rápido ciclo de desarrollo: No es necesario compilar el código, lo que acelera el proceso de desarrollo y depuración.
- Flexibilidad: Los cambios en el código se reflejan inmediatamente en la ejecución, lo que facilita la experimentación y la depuración.
- Portabilidad: Los programas interpretados suelen ser más portátiles, ya que el intérprete puede ejecutar el mismo código en diferentes plataformas sin necesidad de recompilar.


Desventajas de la interpretación:

- Rendimiento: La interpretación suele ser más lenta que la ejecución de código compilado, ya que cada instrucción se analiza y ejecuta en tiempo real.
- Detección de errores tardía: Los errores pueden pasar desapercibidos hasta que el intérprete encuentre la línea que los contiene durante la ejecución.
- Dependencia del intérprete: El intérprete debe estar presente en el sistema para ejecutar el código, lo que puede limitar la portabilidad del programa en entornos donde el intérprete no está disponible.




## Ejercicio 4: 

### Explique claramente la diferencia entre un error sintáctico y uno semántico. Ejemplifique cada caso.


### Errores sintácticos:

Los errores sintácticos son errores de las reglas de gramática del lenguaje de programación. Ocurren cuando el código no sigue la estructura correcta o las convenciones de sintaxis del lenguaje. Estos errores generalmente se detectan durante la fase de compilación.

Ejemplo de error sintáctico en Python:



```py
    # Error de sintaxis: Falta un paréntesis de cierre
    print("Hola mundo"
```

En este ejemplo, falta un paréntesis de cierre al final de la llamada a la función print(). Esto viola la sintaxis del lenguaje Python y generará un error sintáctico al intentar compilar o ejecutar el código.


### Errores semánticos:

Los errores semánticos son errores en el significado o la lógica del código. Aunque el código puede estar escrito correctamente desde el punto de vista sintáctico, puede producir resultados inesperados o incorrectos debido a errores semánticos. Estos errores generalmente se detectan durante la ejecución del programa.

Ejemplo de error semántico en Python:

```py
    # Error semántico: La variable 'a' no está definida
    b = a + 5
    print(b)
```


## Ejercicio 5: 

### Sean los siguientes ejemplos de programas. Analice y diga qué tipo de error se produce (Semántico o Sintáctico) y en qué momento se detectan dichos errores (Compilación o Ejecución).

Aclaración: Los valores de la ayuda pueden ser mayores.

a) Pascal

```Pascal

    Program P
    var 5: integer; // Sintactico : El nombre de la variable no puede comenzar con un número
    var a:char; //Sintactico : La palabra reservada VAR va solo una vez
    Begin
        for i:=5 to 10 do // Semantico : i no esta declarada
        begin
            write(a); // Semantico : se intenta imprimir a pero no esta inicializada
            a=a+1; // Sintactico : La asignación debe ser con ":=" // Semantico: no se puede sumar a una variable de tipo char un entero
        end;
    End.

    Ayuda: Sintáctico 2, Semántico 3
```



b) Java:

```Java

    public String tabla(int numero, arrayList<Boolean> listado){ // Sintactico: ArrayList va con mayúscula.
        String result = null;
        for(i = 1; i < 11; i--) { // Semantico : no esta declarada // Logico : i deberia aumentar no disminuir
            result += numero + "x" + i + "=" + (i*numero) + "\n"; // Sintactico : La variable i no esta declarada
            listado.get(listado.size()-1)=(BOOLEAN) numero>i; //Semantico: Se está intentando asignar un valor booleano a un elemento de la lista //Sintactico : No existe wl tipo BOOLEAN deberia ser Boolean o boolean
        }
        return true; // Semantico : la funcion debe retornar un String
    }
    Ayuda: Sintácticos 4, Semánticos 3, Lógico 1
```


c) C

```C
    # include <stdio.h>
    int suma; /* Esta es una variable global */
    int main()
    {  
        int indice;
        encabezado; // Error sintactico: Falta el símbolo '#' antes de 'encabezado'
        for (indice = 1 ; indice <= 7 ; indice ++) //Error sintactico : Para incluir sentencias dentro de un for se debe cerrar entre {}
            cuadrado (indice);
        
        final(); //Error semantico: no esta declarada Llama a la función final */ // Error sintactico: Este comentario está mal colocado
        return 0;
    }

    cuadrado (numero) // Error sintactico: Se debe especificar el tipo de dato de los parámetros || Error sintactico: las llaves de la funcion cuadrado estan mal colocadas || Error semantico: la función cuadrado está mal declarada. || Error semantico: falta el tipo de parámetro que es número en la definición de la función cuadrado. || Error semantico: la función cuadrado no tiene tipo de retorno
    int numero; // Error semantico : Se debe declarar antes o dentro de cuadrado(numero)
    {   
        int numero_cuadrado;
        numero_cuadrado == numero * numero; // Error semantico: Debería ser una asignación, no una comparación
        suma += numero_cuadrado;
        printf("El cuadrado de %d es %d\n", numero, numero_cuadrado);
    }

    Ayuda: Sintácticos 2, Semánticos 6
```


d)Python
```py
    #!/usr/bin/python
    print "\nDEFINICION DE NUMEROS PRIMOS"
    r = 1
    while r = True: # Sintantico: Se debe usar el operador de comparación "=="
        N = input("\nDame el numero a analizar: ")
        i = 3
        fact = 0
        if (N mod 2 == 0) and (N != 2): # Semántico: "mod" no es un operador en Python para calcular el módulo. Debería ser "%".
            print "\nEl numero %d NO es primo\n" % N
        else:
            while i <= (N^0.5): # Semántico: El operador "^" no esta bien. Debería ser "**".
                if (N % i) == 0:
                    mensaje="\nEl numero ingresado NO es primo\n" % N # Semántico: Se debería eliminar "% N".
                    msg = mensaje[4:6]
                    print msg # Sintantico : faltan parentecis
                    fact = 1
                    i+=2    
                if fact == 0:
                    print "\nEl numero %d SI es primo\n" % N  # Sintantico : faltan parentecis. 
                    # Semántico: Se debería eliminar "% N".
        r = input("Consultar otro número? SI (1) o NO (0)--->> ")

    Ayuda: Sintácticos 2, Semánticos 3
```


e) Ruby

```Ruby

    def ej1
        puts 'Hola, ¿Cuál es tu nombre?'
        nom = gets.chomp
        puts 'Mi nombre es ', + nom # Semantico : La coma esta fuera de las comillas
        puts 'Mi sobrenombre es 'Juan'' # Semantico : Estan mal cerrada las comillas
        puts 'Tengo 10 años'
        meses = edad * 12 # Semantico : edad no esta definida todavia 
       	dias = 'meses' *30 #Error Semantico: Para calcular la cantidad de días, se está multiplicando un string por un entero, cuando en realidad se debe multiplicar el valor entero de meses por 30. Se detecta en ejecución.
        hs= 'dias * 24'
        puts 'Eso es: ' + meses.to_s + ' meses o ' + dias.to_s + ' días o ' + hs.to_s + ' horas'
        puts 'Vos cuántos años tenés'
        edad2 = gets.chomp
        edad = edad + edad2.to_i # Semantico : edad todavia no tiene ningun valor asignado
        puts 'Entre ambos tenemos ' + edad.to_s + ' años'
        puts '¿Sabes que hay ' + nom.length.to_s + ' caracteres en tu nombre, ' + nom + '?'
    end

    Ayuda: Semánticos +4
```

## Ejercicio 5:


## Dado el siguiente código escrito en pascal. Transcriba la misma funcionalidad de acuerdo al lenguaje que haya cursado en años anteriores. Defina brevemente la sintaxis (sin hacer la gramática) y semántica para la utilización de arreglos y estructuras de control del ejemplo.

```Pascal

    Procedure ordenar_arreglo(var arreglo: arreglo_de_caracteres; cont: integer);
    var
        i: integer;
        ordenado: boolean;
        aux: char;
    begin
        repeat
            ordenado := true;
            for i := 1 to cont - 1 do
            begin
                if ord(arreglo[i]) > ord(arreglo[i + 1]) then
                begin
                    aux := arreglo[i];
                    arreglo[i] := arreglo[i + 1];
                    arreglo[i + 1] := aux;
                    ordenado := false;
                end;
            end;
        until ordenado;
    end;


```



Observación: Aquí sólo se debe definir la instrucción y qué es lo que hace cada una; detallando alguna particularidad del lenguaje respecto de ella. Por ejemplo el for de java necesita definir una variable entera, una condición y un incremento para dicha variable.

```java
   
    void ordenarArreglo(char[] arreglo, int cont) {
        
        int i;
        boolean ordenado;
        char aux;

        
        do {
            ordenado = true; 

           
            for (i = 0; i < cont - 1; i++) {
              
                if (arreglo[i] > arreglo[i + 1]) {
                    aux = arreglo[i];
                    arreglo[i] = arreglo[i + 1];
                    arreglo[i + 1] = aux;
                    ordenado = false; 
                }
            }
        } while (!ordenado); 
    }

```


- void ordenarArreglo(char[] arreglo, int cont): Función llamada ordenarArreglo que toma como argumentos un arreglo de caracteres arreglo y un entero cont que representa la cantidad de elementos en el arreglo.

- do { ... } while (!ordenado);: Utiliza un bucle do-while.

- for (i = 0; i < cont - 1; i++) { ... }: Utiliza un bucle for para iterar sobre el arreglo y comparar elementos.

- if (arreglo[i] > arreglo[i + 1]) { ... }: Compara dos elementos en el arreglo y realiza un intercambio si el elemento actual es mayor que el siguiente.

- aux = arreglo[i]; arreglo[i] = arreglo[i + 1]; arreglo[i + 1] = aux; : Intercambia los elementos.

```py
    def ordenar_arreglo(arreglo, cont):
        ordenado = False
        while not ordenado:
            ordenado = True
            for i in range(cont - 1):
                if ord(arreglo[i]) > ord(arreglo[i + 1]):
                    arreglo[i], arreglo[i + 1] = arreglo[i + 1], arreglo[i]
                    ordenado = False
```

- def ordenar_arreglo(arreglo, cont): Función llamada ordenar_arreglo que toma como argumentos un arreglo de caracteres arreglo y un entero cont que representa la cantidad de elementos en el arreglo.

- while not ordenado:: Bucle while.

- for i in range(cont - 1):: Bucle for para iterar sobre el arreglo y comparar elementos.

- if ord(arreglo[i]) > ord(arreglo[i + 1]):: Compara dos elementos en el arreglo y realiza un intercambio si el elemento actual es mayor que el siguiente.

- aux = arreglo[i], arreglo[i] = arreglo[i + 1], arreglo[i + 1] = aux: Intercambia los elementos.

## Ejercicio 6: 

### Explique cuál es la semántica para las variables predefinidas en lenguaje Ruby self y nil. ¿Qué valor toman; cómo son usadas por el lenguaje?

Self:

- Es una variable especial que hace referencia al objeto actual en el contexto actual.
- Se utiliza para acceder a métodos y variables de instancia del objeto actual.
- Fuera del contexto de cualquier objeto, self se refiere a la clase en la que se está definiendo el código.

nil:

- Es un objeto que representa la ausencia de un valor o la falta de definición de un objeto.
- Es el único objeto de clase NilClass en Ruby y es utilizado para indicar la ausencia de un valor o para inicializar variables que aún no tienen un valor asignado.
- Se usa como un valor predeterminado o para manejar casos en los que no hay un resultado válido.
- Se evalúa como falso en contextos booleanos.
- Es un objeto y puede tener métodos definidos en su clase NilClass, lo que permite realizar operaciones específicas en nil, como nil.to_s para obtener una representación en cadena de nil.




## Ejercicio 7:
### Determine la semántica de null y undefined para valores en javascript.¿Qué diferencia hay entre ellos?

Son dos valores que representan la ausencia de valor, pero tienen algunas diferencias importantes en cuanto a su semántica y su uso:

null:

- Es un valor que indica explícitamente la ausencia de un valor o la no existencia de un objeto.
- Es un valor primitivo en JavaScript y es asignado a variables o propiedades cuando se quiere indicar que no hay ningún valor válido presente.
- A diferencia de undefined, null es un valor asignable, lo que significa que se puede asignar explícitamente a una variable para indicar que no hay ningún valor.

Undefined:

- Indica que una variable ha sido declarada pero no inicializada, o que una propiedad de un objeto no existe o no tiene un valor asignado.
- Es un valor primitivo en JavaScript que representa la ausencia intencional o no intencional de un valor.
- Las variables en JavaScript que no han sido inicializadas tienen automáticamente el valor undefined.
- Cuando se accede a una propiedad de un objeto que no existe, JavaScript devuelve undefined.
- A diferencia de null, no es un valor asignable.

En resumen son ambos valores que indican la ausencia de valor en JavaScript, pero null se utiliza típicamente cuando se desea indicar explícitamente que no hay un valor válido presente, mientras que undefined se utiliza para variables no inicializadas o propiedades que no existen en un objeto. Además, null es asignable, mientras que undefined no lo es.

## Ejercicio 8: 
### Determine la semántica de la sentencia break en C, PHP, javascript y Ruby. Cite las características más importantes de esta sentencia para cada lenguaje

**C**:

En C, la sentencia break se utiliza dentro de bucles for, while y do-while para salir prematuramente del bucle. Cuando se encuentra una sentencia break dentro de un bucle, el control del programa se transfiere inmediatamente fuera del bucle y la ejecución continúa con la primera línea de código después del bucle. Es útil para salir de un bucle antes de que se complete su iteración completa, basado en alguna condición específica.

**PHP**:

En PHP se utiliza de manera similar a C, dentro de bucles for, while y do-while. Cuando se encuentra un break, se corta la ejecución de la estructura de control y la ejecución continúa en la línea luego del bucle. Es útil para salir de un bucle antes de que se complete su iteración completa.

**JavaScript**:

En JavaScript su uso no difere mucho del uso en C o PHP. En un bucle etiquetado permite salir de un bucle anidado específico cuando se encuentra una condición adecuada, lo que es útil para controlar flujos de bucles más complejos.

**Ruby**:

En Ruby, el caso es igual. Ruby también admite break con un valor opcional, que puede ser útil para devolver un valor específico cuando se rompe el bucle.

## Ejercicio 9:
### Defina el concepto de ligadura y su importancia respecto de la semántica de un programa. ¿Qué diferencias hay entre ligadura estática y dinámica? Cite ejemplos (proponer casos sencillos)

La ligadura es el momento en que un atributo se asocia con su valor. Es uno de los conceptos más importantes en la semántica de los lenguajes de programación ya que en los programas se trabaja con entidades, y estas entidades deben tener valores para poder usarse, y estos valores son dados a las entidades a través de la ligadura.

**Ligadura estática:**

- Se establece antes de la ejecución.
- No se puede modificar.

`int` en C, define tipos permitidos y cómo se escriben, que se usarán para enteros y lo vincula a operaciones algebraicas.

**Ligadura dinámica:**

1. Se establece durante la ejecución.
2. Se puede modificar durante ejecución de acuerdo a alguna regla específica del lenguaje.

`int a; a =10; a = 96;` El valor de una variable entera se liga en ejecución y puede cambiar muchas veces