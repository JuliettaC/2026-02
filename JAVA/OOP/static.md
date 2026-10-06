---
tags:
  - java
  - java/oop
status: aprendido
aliases:
  - "Static keywords"
  - "Static Keyword"
---

# static
> [!summary] En una frase
> Un miembro static pertenece a la clase, en lugar de a cada objeto individual.

## Ejemplo completo
Guarda como `Curso.java`.

```java
public class Curso {
    static int inscritos = 0;

    Curso() {
        inscritos++;
    }

    static int total() {
        return inscritos;
    }

    public static void main(String[] args) {
        Curso primero = new Curso();
        Curso segundo = new Curso();
        System.out.println(Curso.total()); // 2
    }
}
```

El campo inscritos se comparte entre instancias de esta clase. total es un [[Atributos y métodos|método]] de clase; no hay una copia del método por cada objeto.

## Errores comunes
- Usa `Clase.miembro` para dejar claro que es static.
- Un método static no tiene this ni puede usar directamente un campo de instancia sin una referencia a un objeto.
- static no significa constante: inscritos cambia. Para impedir reasignación se utiliza [[final]].

Fuente: [JLS §8.3.1.1 y §8.4.3.2](https://docs.oracle.com/javase/specs/jls/se25/html/jls-8.html).
