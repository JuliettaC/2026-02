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
> [!summary] Qué es
> Un miembro static pertenece a la clase; un miembro de instancia pertenece a cada objeto.

## Ejemplo completo

Guarda como **Curso.java**.

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

**Cómo funciona:** inscritos se comparte entre ambos objetos; total() se invoca desde la clase.

## Errores comunes

- Usa **Clase.miembro** para expresar que es static.
- Un método static no tiene this; necesita una referencia para usar miembros de instancia.
- static no significa constante: **final** impide reasignar.

## Estado compartido e inicialización

| Elemento | Qué recordar |
|---|---|
| Lista static | Compartida por todos; no sirve para préstamos propios de cada socio |
| static final | Fija la referencia, no congela la lista |
| Bloque static | Inicializa la clase, no cada objeto |
| Campos y bloques static | Se inicializan en orden textual |
| Inicializador de instancia | Prepara cada objeto junto con su construcción |
| Preparación de JVM | Asigna valores por defecto antes de la inicialización explícita |

## Relacionado

[[Atributos y métodos|método]] · [[final]]

Fuente: [JLS §8.3.1.1 y §8.4.3.2](https://docs.oracle.com/javase/specs/jls/se25/html/jls-8.html).
