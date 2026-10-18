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

## Estado compartido e inicialización
Una lista static en Socio pertenece a la clase: todos los socios consultan la misma lista. Si cada socio necesita préstamos propios, el campo debe pertenecer a cada instancia. Combinar static con final impide sustituir la referencia, pero no separar el contenido por persona ni evitar modificaciones a la lista.

Un bloque `static { ... }` ejecuta inicialización de clase, no una vez por objeto. Los inicializadores de campos static y bloques static se ejecutan en orden textual durante esa inicialización. Los inicializadores de instancia preparan cada objeto y se relacionan con sus constructores. La preparación de la JVM asigna primero valores por defecto; no debe confundirse con ejecutar estas inicializaciones explícitas.

Fuente: [JLS §8.3.1.1 y §8.4.3.2](https://docs.oracle.com/javase/specs/jls/se25/html/jls-8.html).
