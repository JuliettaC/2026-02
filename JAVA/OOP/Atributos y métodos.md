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
> [!summary] Qué es
> Los campos guardan estado; los métodos definen acciones y cálculos.

## Sintaxis y ejemplo completo

Guarda como **Contador.java**.

```java
public class Contador {
    int valor;

    void aumentar(int cantidad) {
        this.valor = this.valor + cantidad;
    }

    int obtenerValor() {
        return valor;
    }

    public static void main(String[] args) {
        Contador contador = new Contador();
        contador.aumentar(2);
        System.out.println(contador.obtenerValor()); // 2
    }
}
```

| Elemento | Función |
|---|---|
| Campo | Dato del objeto |
| Método | Retorno, nombre, parámetros y cuerpo |
| void | No devuelve valor |
| Parámetro / argumento | Variable declarada / valor recibido |

**Importante:** llamar requiere paréntesis. Un retorno no void debe dar un valor compatible en toda ruta que termine normalmente.

## this

**Qué es:** referencia al objeto actual; distingue el campo del parámetro.

```java
class Alumno {
    String nombre;

    void asignarNombre(String nombre) {
        this.nombre = nombre;
    }
}
```

**Duda resuelta:** nombre = nombre se asigna el parámetro a sí mismo; this.nombre = nombre actualiza el campo hasta que vuelva a cambiar.

## Firma, argumentos y paso por valor

- **Firma:** nombre y tipos de parámetros, con reglas adicionales para genéricos; el retorno solo no distingue sobrecargas.
- Argumentos: respeta **cantidad, orden y tipos**. Intercambiar dos String puede compilar y cambiar el significado.
- **Java pasa por valor:** copia el primitivo o la referencia.
- Reasignar un parámetro no reasigna la variable del llamador; mutar el objeto compartido sí puede verse desde fuera.
- **return** termina la llamada; mostrar un dato no es devolverlo.
- Comprueba el resultado de éxito antes de anunciar que una operación funcionó.

## Relaciones con otros temas

El constructor prepara la instancia y **no tiene tipo de retorno**; static identifica miembros de clase.

## Relacionado

[[Clases y objetos#Constructor|constructor]] · [[Variables y scopes]] · [[static]] · [[Modificadores de acceso]]

Fuente: [JLS §8.3–8.4](https://docs.oracle.com/javase/specs/jls/se25/html/jls-8.html).
