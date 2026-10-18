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

## Conversión de texto y configuración regional
`Double.parseDouble(texto)` interpreta una representación numérica con punto decimal y no adopta la configuración regional de un objeto Locale creado en otro lugar. El texto `"4,5"` del 14 de octubre no se convierte automáticamente en 4.5: produce NumberFormatException. Debe definirse el formato de entrada y usar un analizador regional cuando se quiera admitir coma decimal. Cambiar cualquier coma por punto sin controlar agrupaciones puede interpretar incorrectamente otros formatos.

Scanner permite configurar su Locale; NumberFormat también permite analizar formatos regionales. Si se usa NumberFormat para validar un campo completo, debe comprobarse que se consumió toda la entrada, porque puede aceptar solo un prefijo. Tras convertir hay que validar el rango y, cuando corresponda, que el número sea finito. Parsear correctamente y cumplir las reglas del modelo son comprobaciones diferentes.

## Salida con printf y Locale
`System.out.printf(locale, formato, argumentos)` usa marcadores: `%d` espera tipos enteros compatibles, `%f` espera tipos de punto flotante compatibles, `%s` representa texto y `%n` genera el salto de línea de la plataforma. `%.1f` muestra una cifra decimal y `%%` imprime el signo de porcentaje. El modificador de agrupación `,` depende del locale; no convierte el argumento a otro tipo.

Un marcador incompatible con el argumento puede producir IllegalFormatConversionException durante la ejecución. En el informe de préstamos, recibir una multa int con `%f` no es compatible: debe elegirse un marcador acorde con el dato o definir una conversión intencional. Mostrar menos decimales tampoco modifica el valor almacenado.

## Entrada, evento y modelo
Los métodos escribirRut o escribirCodigo actualizan el estado de una pantalla simulada; clicGuardar o clicRegistrar representan una reacción a un evento. La validación de la pantalla mejora la interacción, pero el modelo debe proteger sus propias reglas porque puede llamarse desde otros lugares.

Si botonHabilitado devuelve true cuando los datos permiten actuar, la rama que informa que faltan datos debe ejecutarse cuando esa condición sea falsa. Tras llamar a una operación que devuelve boolean u Optional, revisa el resultado antes de mostrar éxito. Estas incoherencias pueden compilar y pertenecen al razonamiento explicado en [[Tipos de errores]].

Fuentes adicionales: [Double.parseDouble](https://docs.oracle.com/en/java/javase/25/docs/api/java.base/java/lang/Double.html#parseDouble(java.lang.String)), [NumberFormat](https://docs.oracle.com/en/java/javase/25/docs/api/java.base/java/text/NumberFormat.html) y [Formatter](https://docs.oracle.com/en/java/javase/25/docs/api/java.base/java/util/Formatter.html).
