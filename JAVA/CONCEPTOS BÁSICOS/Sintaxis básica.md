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
> [!summary] Qué es
> Java distingue mayúsculas; las llaves delimitan bloques y muchas instrucciones terminan con punto y coma.

## Ejemplo completo

Guarda como **Hola.java**.

```java
public class Hola {
    public static void main(String[] args) {
        int edad = 20;
        System.out.println("Edad: " + edad);
    }
}
```

## Puntos clave

| Elemento | Qué recordar |
|---|---|
| Mayúsculas | System y system son nombres distintos |
| { } | Delimitan bloques y scopes |
| ; | Cierra muchas instrucciones; no cada bloque |
| // / /* ... */ | Comentario de línea / bloque |
| Keywords | class, public, static, void, int y new son reservadas |
| Identificadores | No empiezan con número |
| Números | 1_000 es mil; 1.000 es decimal; 1_000_ es inválido |

## Rutas de archivos

En un String, la barra invertida inicia escapes: **\n** es salto de línea; una barra literal se escribe doble.

```java
String ruta = "C:/datos/prestamos.txt";
String alternativa = "C:\\datos\\prestamos.txt";
System.out.println(ruta);
System.out.println(alternativa);
```

**Importante:** en estos ejemplos de Windows ambas rutas sirven. Una barra sin escapar puede crear un escape inválido o cambiar el contenido.

## Literales, escapes y diagnóstico

- String usa **comillas dobles rectas**; char, **simples**. Las tipográficas no sirven de delimitador.
- Un exponente con e/E necesita dígitos; un escape Unicode necesita **cuatro dígitos hexadecimales**.
- **\d no es un escape de String Java**. Para enviarlo a una expresión regular, escapa la barra en el fuente.
- Una falta de delimitador y un literal mal formado pueden pertenecer a categorías de error distintas.

## Relacionado

[[Ciclo de vida de un programa en Java]] · [[Variables y scopes|variables locales]] · [[Clases y objetos]] · [[Atributos y métodos]] · [[static]] · [[Tipos de errores]]

Fuente: [JLS §3.8–3.10](https://docs.oracle.com/javase/specs/jls/se25/html/jls-3.html).
