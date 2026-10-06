---
tags:
  - java
  - java/oop
status: aprendido
aliases:
  - "Clase"
  - "Objeto"
  - "Classes and Objects"
  - "constructor"
---

# Clases y objetos
> [!summary] En una frase
> Una clase define una plantilla; un objeto es una instancia concreta con su propio estado.

Una clase describe [[Atributos y métodos|datos y acciones]]. Las [[Convenciones de nombres (Naming Conventions)|convenciones]] usan PascalCase para clases y camelCase para variables que referencian objetos.

## Constructor
Prepara el objeto al crearlo. Tiene el nombre de la clase y **no declara tipo de retorno**, ni siquiera void. Se utiliza habitualmente con new.

## Ejemplo completo
Guarda como `Auto.java`.

```java
public class Auto {
    String marca;

    Auto(String marca) {
        this.marca = marca;
    }

    public static void main(String[] args) {
        Auto primero = new Auto("Toyota");
        Auto segundo = new Auto("Kia");
        System.out.println(primero.marca);
        System.out.println(segundo.marca);
    }
}
```

Cada objeto tiene su marca; las variables primero y segundo guardan referencias. [[Atributos y métodos#this|this.marca]] identifica el campo del objeto actual.

## Puntos clave
- `Auto primero;` declara una variable, no crea el objeto.
- `new Auto("Toyota")` crea la instancia y ejecuta su constructor.
- Si no declaras ningún constructor en una clase común, Java proporciona uno sin parámetros. Si declaras uno, no agrega automáticamente otro sin parámetros.
- new es la forma básica estudiada, pero no significa que todo objeto de Java deba crearse escribiendo new: un literal String también representa un objeto.

[[Modificadores de acceso]] limita quién puede usar una clase o constructor.

Fuente: [JLS §8.8](https://docs.oracle.com/javase/specs/jls/se25/html/jls-8.html#jls-8.8).
