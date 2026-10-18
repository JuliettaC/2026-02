---
tags:
  - java
  - java/fundamentos
status: aprendido
aliases:
  - "I/O"
  - "Scanner"
---

# Entrada y salida de datos (I/O)
> [!summary] Qué es
> La entrada obtiene datos; la salida muestra resultados. Scanner permite leer desde consola.

## Salida

| Operación | Efecto |
|---|---|
| System.out.print | Sin salto de línea |
| System.out.println | Con salto de línea |
| System.out.printf | Salida con formato |

## Ejemplo completo

Guarda como **Entrada.java**.

```java
import java.util.Scanner;

public class Entrada {
    public static void main(String[] args) {
        Scanner teclado = new Scanner(System.in);
        System.out.print("Nombre: ");
        String nombre = teclado.nextLine();
        System.out.println("Hola, " + nombre);
    }
}
```

## Confusión común

- **nextInt():** lee un entero; una entrada incompatible puede lanzar una excepción.
- Después, **nextLine()** lee el resto de esa línea, a menudo vacío: consúmelo antes de pedir otra línea.

## Conversión de texto y configuración regional

- **Double.parseDouble:** usa punto decimal; «4,5» causa NumberFormatException.
- Crear un Locale aparte **no cambia** parseDouble.
- **Scanner con Locale / NumberFormat:** permiten formatos regionales.
- NumberFormat puede aceptar un prefijo: comprueba que consumió **todo el campo**.
- No reemplaces comas indiscriminadamente: podrían ser separadores de miles.
- Tras convertir, valida **rango** y, si corresponde, **valor finito**.

## Salida con printf y Locale

| Marcador | Uso |
|---|---|
| %d | Enteros compatibles |
| %f / %.1f | Punto flotante compatible / una cifra decimal |
| %s | Texto |
| %n / %% | Salto de línea / signo de porcentaje |
| , | Agrupación según Locale |

**Importante:** %f con un int puede lanzar IllegalFormatConversionException. Formatear no convierte tipos ni cambia el valor almacenado.

## Entrada, evento y modelo

- **escribirRut / escribirCodigo:** actualizan el campo; **clicGuardar / clicRegistrar:** reaccionan al evento.
- Pantalla y modelo validan; el **modelo protege sus reglas** ante cualquier llamador.
- Si botonHabilitado es true, los datos permiten actuar: el aviso de incompletos corresponde al caso contrario.
- Revisa el boolean u Optional devuelto **antes de anunciar éxito**.

## Relacionado

[[Packages]] · [[Strings|String]] · [[Exception Handling|excepción]] · [[Tipos de errores]]

Fuente: [API Scanner](https://docs.oracle.com/en/java/javase/25/docs/api/java.base/java/util/Scanner.html).

Fuentes adicionales: [Double.parseDouble](https://docs.oracle.com/en/java/javase/25/docs/api/java.base/java/lang/Double.html#parseDouble(java.lang.String)), [NumberFormat](https://docs.oracle.com/en/java/javase/25/docs/api/java.base/java/text/NumberFormat.html) y [Formatter](https://docs.oracle.com/en/java/javase/25/docs/api/java.base/java/util/Formatter.html).
