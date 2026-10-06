---
tags:
  - java
  - java/fundamentos
status: aprendido
aliases:
  - "Loops"
  - "for"
  - "while"
---

# Bucles
> [!summary] En una frase
> Repiten instrucciones controlando una condición o recorriendo elementos.

## for
Útil con un contador. Sus tres partes se separan con `;`.

```java
for (int i = 0; i < 3; i++) {
    System.out.println(i);
}
```

Inicialización una vez; condición antes de cada vuelta; actualización al terminar el cuerpo, salvo que se abandone el bucle.

## for-each
Recorre [[Arreglos (Arrays)|arrays]] sin administrar índices; también puede recorrer colecciones, mencionadas en clase y pendientes de estudio.

```java
int[] notas = {5, 6, 7};
for (int nota : notas) {
    System.out.println(nota);
}
```

## while
Evalúa primero: puede ejecutar cero vueltas. Es útil cuando la repetición depende de una condición.

```java
int numero = 0;
while (numero < 3) {
    System.out.println(numero);
    numero++;
}
```

## do...while
Ejecuta el cuerpo antes de evaluar: al menos una vez si se alcanza la sentencia.

```java
int numero = 10;
do {
    System.out.println("El numero es: " + numero);
} while (numero < 5);
```

## Errores comunes
- No actualizar lo que controla un while puede producir un bucle infinito.
- Revisa `i < datos.length`, no `i <= datos.length`.
- El `;` final del do...while sí se necesita.
- [[Variables y scopes]] ayuda a decidir dónde inicializar un acumulador; [[Operadores lógicos]] combina condiciones.

Fuente: [JLS §14.12–14.14](https://docs.oracle.com/javase/specs/jls/se25/html/jls-14.html).
