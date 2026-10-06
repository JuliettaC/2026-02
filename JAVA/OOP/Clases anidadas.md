---
tags:
  - java
  - java/oop
status: aprendido
aliases:
  - "Nested Classes (Clases Anidadas)"
  - "Nested Classes"
  - "inner class"
---

# Clases anidadas
> [!summary] En una frase
> Una clase anidada se declara dentro de otra y permite agrupar tipos relacionados.

La que contiene la declaración es la clase externa (outer class). No toda clase anidada es inner: una clase miembro static es anidada, pero no es una inner class.

## Ejemplo completo
Guarda como `Externa.java`.
```java
public class Externa {
    private int valor = 10;

    class Interna {
        int leer() {
            return valor;
        }
    }

    static class Auxiliar {
        int doble(int numero) {
            return numero * 2;
        }
    }

    public static void main(String[] args) {
        Externa externa = new Externa();
        Externa.Interna interna = externa.new Interna();
        Externa.Auxiliar auxiliar = new Externa.Auxiliar();
        System.out.println(interna.leer());     // 10
        System.out.println(auxiliar.doble(3));  // 6
    }
}
```

- Interna está asociada a una instancia de Externa.
- Auxiliar no necesita una instancia externa.
- Una anidada puede acceder a miembros private dentro del tipo superior. Para campos de instancia, una anidada static necesita una referencia a la instancia externa.

Sirven para agrupar clases con una utilidad ligada a otra. Pueden limitar visibilidad y facilitar mantenimiento, pero anidar no oculta automáticamente una clase: depende de [[Modificadores de acceso]]. El encapsulamiento solo se conserva como mención.

[[static]] explica la pertenencia a la clase; [[Clases y objetos]] explica la instancia.

Fuente: [JLS §8.1.3](https://docs.oracle.com/javase/specs/jls/se25/html/jls-8.html#jls-8.1.3).

