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
> [!summary] Qué es
> Las excepciones interrumpen el flujo normal; try/catch permite responder y throws declara propagación.

## Categorías

| Categoría | Obligación del compilador | Ejemplos |
|---|---|---|
| Checked | Capturar o declarar | IOException, SQLException |
| RuntimeException y subclases | Ninguna de esas dos | ArithmeticException, NullPointerException, ArrayIndexOutOfBoundsException |
| Error y subclases | Ninguna de esas dos | OutOfMemoryError, StackOverflowError |

**Importante:** checked comprueba una obligación al compilar; la excepción se lanza **al ejecutar**. «Fallo externo» y «error de uso» son orientaciones, no definiciones.

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

| Parte | Función |
|---|---|
| try | Contiene operaciones que pueden fallar |
| catch | Responde a una excepción compatible; no impide que ocurra |
| finally | Limpieza al abandonar try/catch, incluso por return o excepción |

> [!warning] Importante
> finally no se alcanza si el bloque nunca termina y no está garantizado si termina el proceso/JVM. Un return allí puede reemplazar resultados o suprimir excepciones.

## throw y throws

| Palabra | Qué hace |
|---|---|
| throw | Lanza una excepción concreta |
| throws | Declara tipos que pueden propagarse; no captura ni lanza por sí solo |

```java
class Ejemplo {
    static void fallar() throws java.io.IOException {
        throw new java.io.IOException("Fallo de ejemplo");
    }
}
```

**Importante:** throws no puede quedar vacío. Unchecked no exige catch, pero no permite sintaxis inválida.

## Error: matiz importante

- Error se puede capturar, pero recuperar indiscriminadamente fallos graves puede ser inseguro.
- **OutOfMemoryError:** no se satisface una solicitud de memoria; no implica agotar toda la RAM.
- **StackOverflowError:** pila desbordada, frecuentemente por recursión excesiva.
- No todo fallo termina automáticamente la aplicación.

## Propagación y orden de captura

- Sin catch compatible, la excepción **sube al llamador**.
- Captura primero subclases y después superclases; invertirlas puede dejar un catch inalcanzable.
- **NumberFormatException** va antes de **IllegalArgumentException**.
- **IllegalArgumentException:** argumento inválido. **IllegalStateException:** estado que impide operar.

## Recursos y recuperación

- Try-with-resources cierra **AutoCloseable** automáticamente.
- Manejar el fallo exige dejar un estado coherente; mostrar un mensaje no basta.
- Un error lógico puede no lanzar excepción.

## Relacionado

[[JDBC y consultas parametrizadas#Cierre de recursos]] · [[Tipos de errores]] · [[Arreglos (Arrays)]] · [[Strings]] · [[Operadores aritméticos básicos]] · [[Operadores lógicos]] · [[Ciclo de vida de un programa en Java]]

Fuentes: [JLS §11](https://docs.oracle.com/javase/specs/jls/se25/html/jls-11.html) y [§14.20.2](https://docs.oracle.com/javase/specs/jls/se25/html/jls-14.html#jls-14.20.2).
