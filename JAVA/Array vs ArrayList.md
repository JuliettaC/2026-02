---
tags:
  - java
status: mencionado
---

# Array vs ArrayList
> [!summary] Qué es
> Ambos agrupan elementos ordenados; el array es fijo y ArrayList puede redimensionarse.

## Comparación rápida

| Característica | Array | ArrayList |
|---|---|---|
| Tamaño | Fijo | Dinámico mediante add/remove |
| Elementos | Primitivos o referencias | Referencias |
| Acceso | Índices desde cero | Índices desde cero |
| Cantidad | length | size() |
| Tipo | int[], String[] | ArrayList<String>, por ejemplo |

## Importante

- Los elementos deben ser compatibles: int[] no acepta texto ni asignación directa de double.
- Usa **Integer/Double** para valores primitivos en ArrayList; String no es un envolvente.
- Los genéricos se recomiendan: omitirlos es posible, pero pierde comprobaciones y puede causar fallos posteriores.

![[Pasted image 20260906114943.png]]

![[Pasted image 20260906115457.png]]

## Relacionado

[[Colecciones y genéricos]] · [[Arreglos (Arrays)]] · [[Bucles]]

Fuente de los matices corregidos: [JLS §4.5 y §4.8](https://docs.oracle.com/javase/specs/jls/se25/html/jls-4.html).
