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
> [!summary] En una frase
> print y println muestran datos; Scanner permite leer entrada de consola.

## Salida
- `System.out.println("Texto");`: agrega salto de línea.
- `System.out.print("Texto");`: no agrega salto de línea.

## Ejemplo completo
Guarda como `Entrada.java`.

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

[[Packages]] explica el import. Aquí Scanner lee una línea completa y se almacena como [[Strings|String]].

## Confusión común
Después de `nextInt()`, un `nextLine()` puede leer solo el resto de esa línea, a menudo vacío. Consume ese resto antes de pedir una nueva línea. Si la entrada no es un entero válido, nextInt puede lanzar una [[Exception Handling|excepción]].

Fuente: [API Scanner](https://docs.oracle.com/en/java/javase/25/docs/api/java.base/java/util/Scanner.html).
