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
> [!summary] Qué es
> Son clases declaradas dentro de otra; agrupan tipos relacionados.

## Ejemplo completo

Guarda como **Externa.java**.

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

| Tipo | Instancia externa |
|---|---|
| Interna (inner) del ejemplo | Necesita una |
| Anidada static | No necesita una |

**Importante:**

- La que contiene la declaración es la **outer class**.
- Las anidadas pueden acceder a private del mismo tipo superior.
- Una anidada static necesita una referencia para usar campos de instancia externos.
- Anidar no oculta automáticamente: la visibilidad depende del modificador.

## Relacionado

[[Modificadores de acceso]] · [[Herencia, interfaces y composición#Composición y encapsulamiento]] · [[static]] · [[Clases y objetos]]

Fuente: [JLS §8.1.3](https://docs.oracle.com/javase/specs/jls/se25/html/jls-8.html#jls-8.1.3).
