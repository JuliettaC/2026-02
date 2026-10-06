---
tags:
  - java
  - java/oop
status: aprendido
aliases:
  - "Packages (Paquetes en Java)"
  - "package"
  - "import"
---

# Packages
> [!summary] En una frase
> Un package agrupa clases y forma parte de su nombre completo.

## Sintaxis
Ejemplo de archivo `clases/Saludo.java`; package precede a los imports.

```java
package clases;

import java.util.Scanner;

public class Saludo {
    public static void main(String[] args) {
        System.out.println("Hola");
    }
}
```

Scanner se importa como ejemplo de sintaxis; este programa no lo utiliza.

## Puntos clave
- Nombre completo: `paquete.Clase`; por ejemplo java.util.Scanner.
- import permite escribir el nombre corto; no copia código ni crea objetos.
- Dos packages pueden contener clases con el mismo nombre simple; el nombre completo elimina ambigüedad.
- Mención de clase conservada: java.util.Date y java.sql.Date son tipos diferentes; su uso queda pendiente.
- java.util.ArrayList pertenece a java.util; la [[Array vs ArrayList|comparación existente]] conserva esa mención sin desarrollar Collections.
- Sin package se usa un paquete sin nombre (unnamed/default package). En proyectos con varias clases suele preferirse un nombre explícito: recomendación de organización.
- Las carpetas suelen reflejar el package; desde la raíz del ejemplo: `javac -d . clases/Saludo.java` y `java clases.Saludo`.

[[Modificadores de acceso]] explica package-private y protected. [[Entrada y salida de datos (I O)]] muestra Scanner en uso.

Fuente: [JLS §7.4 y §7.5](https://docs.oracle.com/javase/specs/jls/se25/html/jls-7.html).
