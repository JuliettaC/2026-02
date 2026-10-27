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
> [!summary] Qué es
> Guardan elementos compatibles con un tipo, con tamaño fijo e índices desde cero.

## Declarar, crear y acceder

```java
int[] numeros = new int[5];
numeros[0] = 10;
System.out.println(numeros[0]); // 10
System.out.println(numeros.length); // 5
int[] notas = {5, 6, 7};
System.out.println(notas[2]); // 7
```

| Elemento | Significado |
|---|---|
| int[] numeros | Referencia a un array |
| new int[5] | Cinco enteros, inicialmente 0 |
| numeros[i] | Lee o modifica una posición |
| numeros.length | Número de elementos; sin paréntesis |

**Importante:** el array no cambia de tamaño; la variable puede apuntar a otro. Arrays de referencias aceptan objetos compatibles y null; no exige una misma clase concreta ni garantiza distribución física contigua.

## Recorrer

```java
int[] datos = {10, 20};
for (int i = 0; i < datos.length; i++) {
    System.out.println(datos[i]);
}
```

## Errores comunes

- Índices válidos: **0 a length − 1**.
- Array vacío: length 0; ningún índice válido.
- Índice inválido: **ArrayIndexOutOfBoundsException**.
- int[] no acepta String ni asignación directa de double.

## Relacionado

[[Strings]] · [[Bucles]] · [[Exception Handling|ArrayIndexOutOfBoundsException]] · [[Array vs ArrayList]]

Fuente: [JLS §10](https://docs.oracle.com/javase/specs/jls/se25/html/jls-10.html).
