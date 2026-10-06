---
tags:
  - java
  - java/oop
status: aprendido
aliases:
  - "Métodos"
  - "Método"
  - "Atributos"
  - "Attributes and Methods"
  - "this"
---

# Atributos y métodos
> [!summary] En una frase
> Los campos representan datos; los métodos definen acciones o cálculos.

## Sintaxis y ejemplo completo
Guarda como `Contador.java`.

```java
public class Contador {
    int valor;

    void aumentar(int cantidad) {
        this.valor = this.valor + cantidad;
    }

    int obtenerValor() {
        return valor;
    }
// hola

    public static void main(String[] args) {
        Contador contador = new Contador();
        contador.aumentar(2);
        System.out.println(contador.obtenerValor()); // 2
    }
}
```

- Campo: `int valor;`; es parte del estado del objeto.
- Método: tipo de retorno, nombre, parámetros entre `()` y cuerpo.
- `void` indica que no devuelve un valor.
- `int obtenerValor()` debe devolver un int en toda ruta que finalice normalmente.
- cantidad es un parámetro; el 2 de la llamada es un argumento.
- Llamar un método exige paréntesis, incluso sin argumentos.

## this
this se refiere al objeto actual. Cuando el parámetro y el campo se llaman igual:
```java
class Alumno {
    String nombre;

    void asignarNombre(String nombre) {
        this.nombre = nombre;
    }
}
```

`nombre = nombre;` asignaría el parámetro a sí mismo. `this.nombre = nombre;` actualiza el campo; dura mientras no se cambie y el objeto siga existiendo, no «permanentemente».

## Relaciones
Un [[Clases y objetos#Constructor|constructor]] prepara la instancia, pero no es un método con tipo de retorno. [[Variables y scopes]] distingue campos, parámetros y variables locales. [[static]] identifica métodos de clase; [[Modificadores de acceso]] controla visibilidad.

Fuente: [JLS §8.3–8.4](https://docs.oracle.com/javase/specs/jls/se25/html/jls-8.html).
