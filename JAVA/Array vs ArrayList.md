---
tags:
  - java
status: mencionado
---

# Array vs ArrayList
> [!note] Mención de clase conservada
> Este apunte ya existía. No representa que Collections esté completado ni se amplía aquí.

## Array
- Tamaño fijo: cinco casillas siguen siendo cinco.
- Elementos compatibles con el tipo declarado; int[] no acepta texto ni asignación directa de double.
- Posiciones ordenadas e índices desde cero.
- Acepta tipos primitivos y de referencia.

Consulta [[Arreglos (Arrays)]] para ejemplo y recorrido con [[Bucles]].

## ArrayList — comparación original
- Tamaño dinámico; add y remove permiten agregar o quitar elementos.
- Se recomienda declarar el tipo, por ejemplo `ArrayList<String>`; es una recomendación, no una obligación sintáctica.
- El uso sin tipo (raw type) conserva compatibilidad histórica, pero pierde comprobaciones de tipo y puede causar fallos al leer; no causa necesariamente un error en toda ejecución.
- Sus elementos son referencias: se usa Integer para valores int, Double para double o String para texto. No todos los objetos son clases envolventes; String no es un wrapper de un primitivo.

Los detalles de Collections y genéricos quedan pendientes; no se añaden ejemplos nuevos de ArrayList.

Fuente de los matices corregidos: [JLS §4.5 y §4.8](https://docs.oracle.com/javase/specs/jls/se25/html/jls-4.html).

## Material de clase conservado

![[Pasted image 20260906114943.png]]

![[Pasted image 20260906115457.png]]

