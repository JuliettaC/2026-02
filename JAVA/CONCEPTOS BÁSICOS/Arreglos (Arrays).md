---
tags:
  - java
  - java/fundamentos
status: aprendido
aliases:
  - "Arrays"
  - "array"
  - "Arreglos"
---

# Arreglos (Arrays)
> [!summary] En una frase
> Un array guarda elementos de un tipo declarado, tiene tamaño fijo e índices desde cero.

## Declarar, crear y acceder
```java
int[] numeros = new int[5];
numeros[0] = 10;
System.out.println(numeros[0]); // 10
System.out.println(numeros.length); // 5
int[] notas = {5, 6, 7};
System.out.println(notas[2]); // 7
```

- `int numero` guarda un entero; `int[] numeros` declara una referencia a un array.
- `new int[5]` crea cinco elementos, inicialmente 0.
- `numeros[i]` lee o modifica una posición.
- `length` es un campo, sin paréntesis; en [[Strings]] se usa `length()`.
- El array mantiene su tamaño; la variable puede referirse después a otro array.
- En arrays de referencia pueden almacenarse objetos compatibles con el tipo declarado y null. No necesariamente tienen todos la misma clase concreta.
- Java no garantiza aquí un diseño físico de posiciones contiguas de memoria.

## Recorrer
```java
int[] datos = {10, 20};
for (int i = 0; i < datos.length; i++) {
    System.out.println(datos[i]);
}
```

Consulta [[Bucles]] para for-each.

## Errores comunes
- El último índice es `length - 1`; usar `<= length` al recorrer accede fuera del array.
- Un índice inválido produce [[Exception Handling|ArrayIndexOutOfBoundsException]].
- Un array vacío tiene length 0 y ningún índice válido.
- `int[]` no acepta String ni asignación directa de double.

[[Array vs ArrayList]] conserva la comparación breve vista en clase.

Fuente: [JLS §10](https://docs.oracle.com/javase/specs/jls/se25/html/jls-10.html).
