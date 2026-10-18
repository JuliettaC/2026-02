---
tags:
  - java
  - java/excepciones
status: aprendido
aliases:
  - "Exception Handling (Manejo de Excepciones)"
  - "Excepciones"
  - "exception"
  - "try"
  - "finally"
---

# Exception Handling
> [!summary] En una frase
> try/catch permite responder a fallos que interrumpen el flujo normal; throws declara que un método puede propagarlos.

## Categorías
| Categoría | Qué exige el compilador | Ejemplos vistos |
|---|---|---|
| Checked exceptions | Capturar o declarar con throws | IOException, SQLException |
| RuntimeException y sus subclases (unchecked) | No exige capturar ni declarar | ArithmeticException, NullPointerException, ArrayIndexOutOfBoundsException |
| Error y sus subclases (también unchecked) | No exige capturar ni declarar | OutOfMemoryError, StackOverflowError |

Las checked suelen aparecer ante fallos externos; las runtime suelen señalar problemas de uso o lógica. Son orientaciones, no la definición formal de esas categorías. Los errores de sintaxis no son excepciones de ejecución.

> [!note] Recordatorio personal conservado
> «Java deja compilar aunq esté mal»: una excepción unchecked no exige catch; esto no significa que el compilador permita código sintácticamente incorrecto.

## try, catch y finally
```java
int divisor = 0;
try {
    System.out.println(10 / divisor);
} catch (ArithmeticException e) {
    System.out.println("No se puede dividir entre cero");
} finally {
    System.out.println("Fin del intento");
}
```

- try contiene las operaciones.
- catch recibe un fallo compatible con su tipo; no evita que ocurra, permite responder.
- finally se ejecuta cuando el control abandona try/catch, incluso por return o excepción, bajo ejecución normal de la JVM. No es una garantía ante terminación del proceso/JVM; si el bloque nunca termina, no se alcanza.

> [!warning] Evita return en finally
> Puede reemplazar el resultado anterior o suprimir una excepción que se propagaba. Como buena práctica, reserva finally para limpieza.

## throw y throws
- `throw`: lanza una excepción concreta.
- `throws`: declara en la firma qué excepción puede propagarse; no la maneja.

```java
class Ejemplo {
    static void fallar() throws java.io.IOException {
        throw new java.io.IOException("Fallo de ejemplo");
    }
}
```

## Error: matiz importante
Error se puede capturar técnicamente. Como regla de diseño habitual, no intentes recuperar indiscriminadamente errores graves: puede faltar un estado seguro para continuar. No todos cierran automáticamente toda la aplicación.
- OutOfMemoryError: no se puede satisfacer una solicitud de memoria; no equivale necesariamente a agotar toda la RAM del computador.
- StackOverflowError: desborde de la pila, frecuentemente por recursión excesiva.

## Propagación y orden de captura
Si una operación lanza una excepción, se abandona el flujo normal hasta encontrar un catch compatible; si el método no la captura, se propaga al llamador. Los catch se prueban en orden. Un catch de una superclase antes de uno de su subclase haría inalcanzable este último y el compilador lo rechaza.

NumberFormatException hereda de IllegalArgumentException. Por eso, en PantallaNotas, la captura específica del formato debe aparecer antes de la captura general de argumentos inválidos. IllegalArgumentException comunica que un argumento no cumple el contrato; IllegalStateException comunica que el estado actual impide la operación.

Checked significa que el compilador comprueba la obligación de capturar o declarar, no que el fallo ocurra al compilar. Su lanzamiento real ocurre durante la ejecución. Una declaración throws necesita tipos de excepciones después de la palabra clave: no puede dejarse vacía. Declarar throws tampoco provoca por sí mismo un lanzamiento.

## Recursos y recuperación
Try-with-resources automatiza el cierre de recursos AutoCloseable. [[JDBC y consultas parametrizadas#Cierre de recursos]] desarrolla su uso con consultas y resultados. Manejar una excepción debe dejar una respuesta coherente: imprimir un mensaje y continuar no basta si quedó estado parcialmente modificado o se anuncia éxito sin haberlo logrado.

Consulta [[Tipos de errores]] para la clasificación didáctica completa. Un error lógico no necesita lanzar una excepción, y una excepción puede ser una manifestación de una condición externa o de un defecto del programa.

## Relacionado
- [[Arreglos (Arrays)]] y [[Strings]]: índices inválidos.
- [[Operadores aritméticos básicos]]: división entera por cero.
- [[Operadores lógicos]]: proteger el acceso a una referencia null con &&.
- [[Ciclo de vida de un programa en Java]]: distinguir compilación de ejecución.

Fuentes: [JLS §11](https://docs.oracle.com/javase/specs/jls/se25/html/jls-11.html) y [§14.20.2](https://docs.oracle.com/javase/specs/jls/se25/html/jls-14.html#jls-14.20.2).
