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
> [!summary] Qué es
> Una clase define datos y comportamiento; un objeto es una instancia con estado propio.

## Constructor

**Qué hace:** prepara el objeto al crearlo. Tiene el nombre de la clase y **ningún tipo de retorno**, ni void.

## Ejemplo completo

Guarda como **Auto.java**.

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

**Cómo funciona:** cada Auto tiene su marca; primero y segundo guardan referencias.

## Puntos clave

- **Auto primero;** declara una referencia; no crea un objeto.
- **new Auto("Toyota")** crea e inicializa la instancia.
- Sin constructores declarados, una clase común recibe uno sin parámetros.
- Si declaras un constructor, Java no añade otro sin parámetros.
- No todo objeto requiere escribir new: un literal String también representa un objeto.
- Nombres: clase en **PascalCase**; variable que referencia al objeto en **camelCase**.

## Relacionado

[[Atributos y métodos|datos y acciones]] · [[Convenciones de nombres (Naming Conventions)|convenciones]] · [[Atributos y métodos#this|this.marca]] · [[Modificadores de acceso]]

Fuente: [JLS §8.8](https://docs.oracle.com/javase/specs/jls/se25/html/jls-8.html#jls-8.8).
