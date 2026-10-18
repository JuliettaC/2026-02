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
> [!summary] Qué es
> Agrupan clases y forman parte de su nombre completo.

## Sintaxis

Archivo **clases/Saludo.java**: package aparece antes de los imports.

```java
package clases;

import java.util.Scanner;

public class Saludo {
    public static void main(String[] args) {
        System.out.println("Hola");
    }
}
```

**Importante:** Scanner solo ilustra el import; el ejemplo no lo utiliza.

## Puntos clave

| Concepto | Qué recordar |
|---|---|
| Nombre completo | paquete.Clase, como java.util.Scanner |
| import | Permite el nombre corto; no copia código ni crea objetos |
| Nombres repetidos | El nombre completo distingue clases de distintos packages |
| Sin package | Paquete sin nombre; en proyectos suele preferirse uno explícito |

- java.util.Date y java.sql.Date son tipos distintos; su uso detallado queda pendiente.
- ArrayList está en **java.util**.
- Las carpetas suelen reflejar el package.
- Desde la raíz: **javac -d . clases/Saludo.java**; después **java clases.Saludo**.

## Relacionado

[[Array vs ArrayList]] · [[Colecciones y genéricos]] · [[Modificadores de acceso]] · [[Entrada y salida de datos (I O)]]

Fuente: [JLS §7.4 y §7.5](https://docs.oracle.com/javase/specs/jls/se25/html/jls-7.html).
