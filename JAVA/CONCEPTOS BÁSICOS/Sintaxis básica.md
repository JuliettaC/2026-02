---
tags:
  - java
  - java/fundamentos
status: aprendido
aliases:
  - "Basic Syntax"
  - "keywords"
---

# Sintaxis básica
> [!summary] En una frase
> Java distingue mayúsculas y minúsculas y usa llaves para bloques y punto y coma en muchas instrucciones.

## Ejemplo completo
Guarda como `Hola.java`; compila y ejecuta según [[Ciclo de vida de un programa en Java]].

```java
public class Hola {
    public static void main(String[] args) {
        int edad = 20;
        System.out.println("Edad: " + edad);
    }
}
```

## Puntos clave
- `System`, `String` y `system` son nombres distintos.
- `{ }` delimita bloques; las [[Variables y scopes|variables locales]] tienen alcance.
- `;` cierra declaraciones locales y muchas sentencias; no se agrega después de cada bloque.
- `//` comenta una línea y `/* ... */` comenta varias.
- Keywords como `class`, `public`, `static`, `void`, `int` y `new` no pueden ser nombres de variables o clases.
- Un identificador no empieza con un número: `primerTramo`, no `1erTramo`.
- `1_000` representa mil; `1_000_` es inválido. El punto de `1.000` representa un decimal, no un separador de miles.

[[Clases y objetos]] explica `class` y `new`; [[Atributos y métodos]] explica `main` como método; [[static]] explica por qué puede llamarse sin crear un objeto.

## Rutas de archivos
En un literal String, `\` inicia un escape: `\n` significa salto de línea. Para representar una barra invertida debes escribir `\\`.

```java
String ruta = "C:/datos/prestamos.txt";
String alternativa = "C:\\datos\\prestamos.txt";
System.out.println(ruta);
System.out.println(alternativa);
```

En las rutas Windows de tus ejercicios, ambas formas sirven. No escribas una barra invertida literal sin escaparla: podría producir un escape inválido o uno válido con un significado inesperado.

Fuente: [JLS §3.8–3.10](https://docs.oracle.com/javase/specs/jls/se25/html/jls-3.html).
