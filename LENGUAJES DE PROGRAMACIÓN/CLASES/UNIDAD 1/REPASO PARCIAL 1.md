
# NIVEL 1 
**El compilador te avisa**
**Errores que el programa NO alcanza a ejecutar**
*Cinco ejercicios donde el código ni siquiera compila: punto y coma, llaves, mayúsculas, comillas y variables sin inicializar. El compilador es tu primer revisor y aquí trabaja gratis. Objetivo del nivel: entrenar la lectura carácter a carácter antes de que la red de seguridad desaparezca*

ejercicio 1 
Falta una coma en la linea 4

ejercicio 2
falta una llave en la linea 5

ejercicio 3
**Java distingue mayúsculas de minúsculas.**
en el sout falta una mayuscula

ejercicio 4
faltan las doble comillas en el string 

ejercicio 5
1) **En java el signo igual es el operador de asignación**
	La asignación siempre viaja de derecha a izquierda:
	Caja donde se guarda (variable a la izquierda) = Valor o cálculo (a la derecha)
2) **Sin valor por defecto:** En Java, las variables locales (las que están declaradas dentro de un método como `main`) no tienen un valor por defecto (como `0`).
3) **Protección del lenguaje:** Java exige de forma obligatoria que toda variable local reciba un valor explícito antes de ser leída, evitando así arrastrar basura de memoria.
no se le asigno un valor inicial a las variables intentos 

# NIVEL 2
**Errores que ningún compilador puede ver**
*El código es sintácticamente impecable y el programa entrega números creíbles: recorrido con índice de más, división entera, comparación de textos, acumulador mal ubicado y un switch en cascada. Objetivo del nivel: descubrir que "compila" no significa "está bien".*

ejercicio 6

length indica el numero de elementos que tiene un arreglo es un atributo no un método por eso se escribe sin paréntesis

 1) Cuidado con los paréntesis (`.length` vs `.length()`):**
    - **Arreglo:** usa `.length` (sin paréntesis). Escribir `datos.length()` genera un error en el compilador: _`cannot find symbol, method length()`_ (pregunta típica de la prueba).
    - **Texto (`String`):** usa el método `.length()` (con paréntesis).
    - **Listas (`List`, `ArrayList`):** usan el método `.size()`.
2) **Rango de índices (`0` a `length - 1`):**
    - Si un arreglo tiene `length = 4`, sus casillas son únicamente **`0, 1, 2 y 3`**.
    - La posición `4` no existe.

en la linea 4 tiene un menor igual en el length por lo que da una vuelta mas con un dato que no existe haciendo que se caiga

ArrayIndexOutOfBoundsException se traduce al español como **"excepción por índice de matriz fuera de los límites"** 

ejercicio 7

En Java, **la operación a la derecha del signo igual (`=`) se resuelve antes de mirar la variable que recibe el resultado**. El tipo de dato de la variable receptora **no cambia la forma en que se hizo la cuenta**.
Los 3 errores clásicos de cálculo y cómo encontrarlos
 1. División entera silenciosa
- **El síntoma:** El programa compila, corre completo, no lanza ninguna excepción, pero el resultado tiene `.0` y le faltan los decimales reales.
- **Cómo encontrarlo en el examen:**
    1. Busca divisiones (`/`).
    2. Mira los dos operandos a los lados de la barra `/`.
    3. Si ambos son enteros (`int / int`, como `suma / 3`), **la cuenta se hace en enteros y descarta la parte decimal antes de guardarse**.
    ```
    int suma = 17;
    double promedio = suma / 3; // 17 / 3 da 5. Recién después se guarda como 5.0
    ```
- **La corrección:** Forzar al menos un operando a decimal escribiendo `3.0` o usando casteo explícito: `(double) suma / 3`.
 1. Desbordamiento silencioso (_Integer Overflow_)
- **El síntoma:** El programa compila, corre y arroja un número negativo o totalmente absurdo.
- **Cómo encontrarlo en el examen:**
    1. Busca multiplicaciones (`*`) de valores grandes (precios, aranceles, cantidades o segundos).
    2. Revisa el tipo de las variables que se están multiplicando.
    3. Si ambas variables son `int`, Java multiplica en 32 bits (máximo 2 147 483 647). Si el resultado supera ese límite, desborda **antes de guardarse en el `long`**; puede dar un resultado positivo o negativo.
    ```
    int arancel = 5_400_000;
    int alumnos = 800;
    long total = arancel * alumnos; // Desborda a 25_032_704 antes de llegar al long
    ```

- **La corrección:** Convertir a `long` antes de multiplicar: `(long) arancel * alumnos` o usar literales con `L`.

 1. Conversión con pérdida (_Lossy Conversion_)
- **El síntoma:** El programa **ni siquiera compila**; `javac` se detiene con: `possible lossy conversion from double to int`.
- **Cómo encontrarlo en el examen:**
    1. Revisa qué tipo de variable está a la **izquierda** del `=`.
    2. Si la variable receptora es un entero (`int`), pero la cuenta a la derecha incluye algún número con decimales (`double`), el compilador no permite truncar la información a tus espaldas.
    ```
    double suma = 24.8;
    int cantidad = 5;
    int promedio = suma / cantidad; // ERROR: suma/cantidad produce un double, no cabe en int
    ```
- **La corrección:** Declarar la variable receptora como `double`.

 Técnica práctica de auditoría
1. **Tapa el lado izquierdo:** Cubre con el dedo el nombre y el tipo de la variable receptora.
2. **Evalúa solo la derecha:** Determina qué tipos de datos están interactuando (`int` con `int`, o `double` con `int`).
3. **Compara tipos:** Destapa la variable receptora y verifica si el tipo resultante a la derecha cabe en la variable de la izquierda sin perder decimales ni sobrepasar su tamaño.

en la linea 5 hay que pasar todo a double para que no se vuelva loco

ejercicio 8

Referencia: En Java, una **referencia** es un valor que permite localizar un objeto; la **dirección de memoria** es una analogía (piénsalo como una **flecha**) que le dice al programa **dónde encontrar un objeto** guardado en la memoria (el _Heap_). No contiene los datos del objeto directamente dentro de sí, sino el camino para llegar a él.

- **Tipos primitivos (`int`, `double`, `boolean`, `char`):** La variable es una caja que **guarda directamente el valor**.

    int a = 5; // La caja 'a' tiene guardado el número 5
    
- **Tipos de referencia (Objetos, `String`, arreglos `[]`, `List`):** La variable **no guarda los datos**, solo guarda la **dirección o flecha** hacia donde vive ese objeto en la memoria.

    String texto = new String("clave123"); 
    // 'texto' no es la palabra en sí; es una flecha que apunta a esa palabra en memoria

El doble `==` compara valores primitivos; entre referencias compara identidad, no contenido.  

![[Pasted image 20260905104316.png]]

Para comparar contenido de `String` se usa `.equals()`; los primitivos no tienen ese método.
![[Pasted image 20260905104903.png]]

en la linea 5 hay que usar .equals

```java
if (ingresada.equals(correcta)) {
    System.out.println("acceso concedido");
}
```
Fragmento: supone que ingresada y correcta son String y que ingresada no es null.

ejercicio 9

![[Pasted image 20260905105727.png]]

 El acumulador vive fuera del ciclo de boletas y nunca se reinicia entre una y otra. Mueve la declaración del acumulador **adentro del primer ciclo** para que cada boleta comience su cuenta desde cero:

ejercicio 10 
El `break` es el freno de mano que detiene la ejecución y te saca del `switch` inmediatamente; sin él, Java sigue ejecutando en cascada todos los casos que vienen abajo aunque no coincidan.

El **`switch`** es una estructura de control condicional que funciona como un **selector de rutas o interruptor multidireccional**.
En lugar de evaluar condiciones booleanas complejas (verdadero/falso), toma el valor de una variable concreta (un número, carácter o texto) y **salta directamente al bloque `case` que tenga exactamente ese mismo valor**.

ejercicio 11
Si un método puede devolver `null`, pedirle cualquier método con el punto (`.`) revienta en `NullPointerException`; siempre se debe validar con `!= null` antes de usar la referencia".


> [!note] Matices del repaso
> List/ArrayList.size() se conserva como mención. En el switch clásico, break u otra salida evita continuar por casos siguientes. Para un String que puede ser null, valida antes de invocar métodos o usa una comparación desde un literal conocido.


## Consulta de conceptos Java
[[Sintaxis básica]] · [[Strings]] · [[Arreglos (Arrays)]] · [[Operadores aritméticos básicos]] · [[Variables y scopes]] · [[Condicionales (Conditionals)]]
