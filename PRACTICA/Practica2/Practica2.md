
## Ejercicio 1:

![alt text](image-1.png)

## Ejercicio 2: 

### ¿Cuál es la importancia de la sintaxis para un lenguaje? ¿Cuáles son sus elementos?

La sintaxis de un lenguaje de programación es la estructura en que se organizan los distintos
elementos sintácticos, como espacios, identificadores, operadores, etc. Es decir, el orden que tienen
unos con respecto a otros.
Una sintaxis se evalúa según varios criterios: que sea fácil de leer, de escribir, de verificar (chequear
en busca de errores), fácil de traducir y que carezca de ambigüedad. Esta última significa que un
mismo código puede tener 2 o más interpretaciones o traducciones posibles, en cuyo caso no se
puede decidir que alternativa elegir.
Es muy importantes ya que establece las reglas para que el programador se comunique con el
procesador de forma correcta sintácticamente.

- Elementos de la sintáxis
    - Alfabeto o conjunto de caracteres
    - Identificadores
    - Operadores
    - Palabra clave y palabra reservada
    - Comentarios y uso de blancos


## Ejercicio 3: 
### ¿Explique a qué se denomina regla lexicográfica y regla sintáctica?

- Reglas léxicas: Conjunto de reglas para formar las “word”, a partir de los caracteres del
alfabeto

- Reglas sintácticas: Conjunto de reglas que definen como formar las “expresiones” y
“sentencias”

## Ejercicio 4:

### En la definición de un lenguaje, a qué se llama palabra reservadas? ¿A qué son equivalentes en la definición de una gramática? De un ejemplo de palabra reservada en el lenguaje que más conoce. (Ada,C,Ruby,Python,..)

En la definición de un lenguaje de programación, las "palabras reservadas" son aquellas que tienen un significado especial y están reservadas para ser utilizadas por el propio lenguaje. Estas palabras tienen funciones específicas dentro del lenguaje y no pueden ser redefinidas por el usuario para otros propósitos. Son parte de la sintaxis del lenguaje y tienen un significado predefinido

Un ejemplo de palabra reservada en el lenguaje Python es if. En Python, if se utiliza para iniciar una estructura condicional que ejecuta cierto bloque de código si una condición es verdadera. Esta palabra está reservada para este propósito y no se puede utilizar como nombre de variable u otro identificador en el código. 

```py

    x = 10

    if x > 5:
        print("x es mayor que 5")
    else:
        print("x no es mayor que 5")

```
## Ejercicio 5: 
### Dada la siguiente gramática escrita en BNF:
```html

    - G= ( N, T, S, P)
    - N = {<numero_entero>, <digito> }
    - T = {0, 1, 2, 3, 4, 5, 6, 7, 8, 9}
    - S = <numero_entero>
    - P = {
        <numero_entero> ::= <digito><numero_entero> | <numero_entero><digito> | <digito>
        <digito> ::= 0 | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9
    }

```


### a- Identifique las componentes de la misma

- G = ( N, T, S, P) son 4 tupla de Conjunto de reglas finita que define un conjunto infinito de posibles sentencias válidas en el lenguaje.

- N = Conjunto de símbolos no terminales
- T = Conjunto de símbolos terminales
- S = Símbolo distinguido de la gramática que pertenece a N
- P = Conjunto de producciones


### b- Indique porqué es ambigua y corríjala

Es ambigua por <digito><numero_entero> | <numero_entero><digito> La asociativa es por la izquierda o por la derecha, en este caso se estarían generando DOS arboles de derivación

```html

    - G= ( N, T, S, P)
    - N = {<numero_entero>, <digito> }
    - T = {0, 1, 2, 3, 4, 5, 6, 7, 8, 9}
    - S = <numero_entero>
    - P = {
        <numero_entero> ::= <digito><numero_entero> | <digito>
        <digito> ::= 0 | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9
}
```

## Ejercicio 6: 
### Defina en BNF (Gramática de contexto libre desarrollada por Backus- Naur) la gramática para la definición de una palabra cualquiera.



```html

    - G= ( N, T, S, P)
    - N = {<palabra>, <mayuscula>,<minuscula> }
    - T = {A...Z , a...z}
    - S = <palabra>
    - P = {
        <palabra> ::= <mayuscula><palabra> | <minuscula><palabra> | <minusculas> | <mayuscula> 
        <mayuscula> ::= A | B | C | D | E ... | Z 
        <minuscula> ::= a | b | c | d | e ... | z
        }
```
```py

    - G= ( N, T, S, P)
    - N = {<palabra>, <letra> }
    - T = {A...Z , a...z}
    - S = <palabra>
    - P = {
        <palabra> ::= <letra><palabra> | <letra> 
        <letra> ::= A | B | C | D | E ... | Z , a | b | c | d ... | z
    }
```

## Ejercicio 7: 

### Defina en EBNF la gramática para la definición de números reales. Inténtelo desarrollar para BNF y explique las diferencias con la utilización de la gramática EBNF.

```html
    EBNF

    - G= ( N, T, S, P)
    - N = {<real>, <digito> }
    - T = {0,1,2,3,4,5,6,7,8,9,"+","-",","}
    - S = <real>
    - P = {
        <real> ::= [-]{<digito>}+ [,{<digito>}+]
        <digito> ::= 0 | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9
    }
```

```html
    BNF

    - G= ( N, T, S, P)
    - N = {<real>, <entero_sin_signo>,<entero_con_signo>,<digito>,<decimal> }
    - T = {0,1,2,3,4,5,6,7,8,9,"+","-",","}
    - S = <real>
    - P = {
        
        <real> ::= <entero_con_signo> | <entero_con_signo><decimal>
        <entero_con_signo> ::= +<entero_sin_signo> | -<entero_sin_signo> | <entero_sin_signo>
        <entero_sin_signo> ::= <digito> | <digito><entero_sin_signo>
        <decimal> ::= ","<entero_sin_signo>
        <digito> ::= 0 | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9 
        
    }
```

BNF requiere definir muchas mas cosas que en EBNF no son necesarias porque se definen con los meta simbolos
BNF parece ser mas dificil de leer a comparacion de EBNF



## Ejercicio 8: 

### Utilizando la gramática que desarrolló en los puntos 6 y 7, escriba el árbol sintáctico de:

    a. Conceptos


- Opcion 1 :
    ![alt text](image-3.png)
- Opcion 2 :

    ![alt text](image-4.png)

###
    b. Programación

![alt text](image-5.png)

###
    c. 1255869

![alt text](image-7.png)

###
    d. 854,26

![alt text](image-6.png)

###
    e. Conceptos de lenguajes




## Ejercicio 9:

```html

    G = ( N, T, S, P)
    N = {<real>,
         <letra>,
         <identificador>,
         <caracter>,
         <digito>}
    T = {0..9, A..Z, a..z}
    S = <real>
    P = {
        <identificador> ::= <letra> {<caracter>}*
        <caracter> ::= (<letra> | <digito>)
        <letra> ::= (a | ... | z | A | ... | Z)
        <digito> ::= (0 | ... | 9)
}

```

![alt text](image-9.png)


## Ejercicio 10:


### a) Defina con EBNF la gramática para una expresión numérica, dónde intervienen variables y números. Considerar los operadores +, -, * y / sin orden de prioridad. No considerar el uso de paréntesis.

```html

    G = ( N, T, S, P)
    N = {
    <elemento>, 
    <identificador>, 
    <caracter>, 
    <numero>, 
    <digito>, 
    <letra>, 
    }
    T = {0-9, a-Z, +, -, *, /}
    S = <operacion>
    P = {
    <expresion> ::= <elemento> {<termino>}+
    <termino> ::= {(* | / | + | -)<elemento>}


    <elemento> ::= (<identificador> | <numero>)
    <identificador> ::= <letra>{<caracter>}*
    <caracter> ::= <digito> | <letra>
    <numero> ::= {<digito>}+
    <digito> ::= 0 | ... | 9
    <letra> ::= a | ... | z | A | ... Z
    }

``` 


### b) A la gramática definida en el ejercicio anterior agregarle prioridad de operadores.

```html

    G = (N, T, S, P)
    N = {
        <expresion>,
        <operacion>,
        <termino>,
        <factor>,
        <variable>,
        <numero>
    }
    T = {0..9, a-z, A-Z, "+", "-", "*", "/"}
    S = <expresion>
    P = {
        <expresion> ::= <termino> {<sumaResta> <termino>}*
        <termino> ::= <factor> {<multDiv> <factor>}*
        <factor> ::= <variable> | <numero>
        <variable> ::= <letra>{<caracter>}*
        <numero> ::= {<digito>}+
        <sumaResta> ::= ("+" | "-")
        <multDiv> ::= ("*" | "/")
        <digito> ::= 0 | ... | 9
        <letra> ::= a | ... | z | A | ... | Z
        <caracter> ::= <digito> | <letra>
    }

``` 

### c) Describa con sus palabras los pasos y decisiones que tomó para agregarle prioridad de operadores al ejercicio anterior.

la prioridad de operadores a la gramática implica asegurar que las operaciones de multiplicación y división se realicen antes que las operaciones de suma y resta. 


## Ejercicio 11: 


### La siguiente gramática intenta describir sintácticamente la sentencia for de ADA, indique cuál/cuáles son los errores justificando la respuesta.

```html

N = {
    <sentencia_for>,
    <bloque>,
    <variable>,
    <letra>,
    <cadena>,
    <digito>,
    <otro>,
    <operacion>
}

P = {
    <llamada_a_funcion>,
    <numero>,
    <sentencia>
}

P = {
        <sentencia_for> ::= for (i = IN 1..10) loop <bloque> end loop;
        <variable> ::= <letra> | <cadena>
        <cadena> ::= {(<letra> | <digito> | <otro>)}+
        <letra> ::= (a | .. | z | A | .. | Z)
        <digito> ::= (1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9 | 0)
        <bloque> ::= <sentencia> | <sentencia> <bloque> | <bloque> <sentencia>;
        <sentencia> ::= <sentencia_asignacion> | <llamada_a_funcion> | <sentencia_if> | <sentencia_for> | <sentencia_while> | <sentencia_switch>
}

```
La gramatica posee una tupla de 4 (N, T, S, P) en este caso falta definir T y S. Ademas no esta definidas en N las sentencia_asignacion , sentencia_if, sentencia_while.

Ademas faltaria realizar la produccion de aquellas sentencias que faltan o que no estan definidas, como (otro,numero,sentencia_asignacion , sentencia_if, sentencia_while,llamada_a_funcion,sentencia_switch,oprecion)


## Ejercicio 12: 

### R ealice en EBNF la gramática para la definición un tag div en html 5. (Puede ayudarse con el siguiente enlace (https://developer.mozilla.org/es/docs/Web/HTML/Elemento/div)

```html

    G = (N, T, S, P)
    N = {
        <tag>,
        <div>,
        <palabra>,
        <bloque>,
        <letra>
    }
    T = {A | B | C | D | E ... Z | a | b | c | d | e | f | g  ... z}
    S = <tag>
    
    P = {
        <tag>::= <div> [{<bloque>}*] "</div>"
        <div>::= "<div"[{<palabra> '=' <palabra>}*]">"
        <palabra> ::= {<letra>}+
        <bloque>::= <tag> (|) '<'<palabra>'>' {<palabra>}* '</'<palabra>'>'
        <letra>::= A | B | C | D | E ... Z | a | b | c | d | e | f | g  ... z
    }
    


```


## Ejercicio 13: 

### Defina en EBNF una gramática para la construcción de números primos.¿Qué debería agregar a la gramática para completar el ejercicio?


## Ejercicio 14: 

### Sobre un lenguaje de su preferencia escriba en EBNF la gramática para la definición de funciones o métodos o procedimientos (considere los parámetros en caso de ser necesario).

```html

    G = (N, T, S, P)
    N = {
       <function>
        <parametros>
        <palabra>
        <codigo>
        <letra>
        <operadores>
    }
    T = {A | B | C | D | E ... Z | a | b | c | d | e | f | g  ... z}
    S = <function>
    
    P = {
        <function>::= "function" [<parametros>] "{"  {<codigo>}+ "}"
        <parametros>::=  "("{<palabra> ","}*")"
        <palabra>::= {<letra>}+
        <codigo>::=  { {<letra>}+ {<operadores>} {<letra>}+ }* (|) {<letra>}+';'
        <letra>::= A | B | C | D | E ... Z | a | b | c | d | e | f | g  ... z
        <operadores>::= + (|) = (|) - (|) * (|) . (|) / (|) > (|) < 
    }
```


