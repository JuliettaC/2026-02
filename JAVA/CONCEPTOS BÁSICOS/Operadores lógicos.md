---
tags:
  - java
  - java/fundamentos
status: aprendido
aliases:
  - "Operador lógico en condicionales (`&&` vs `&`)"
  - "&&"
  - "AND"
---

# Operadores lógicos
> [!summary] En una frase
> && combina condiciones y evita evaluar la segunda si la primera es falsa.

## && frente a &
| Operador con boolean | Comportamiento |
|---|---|
| `a && b` | Ambas deben ser true; b solo se evalúa si a es true |
| `a & b` | Ambas deben ser true; evalúa las dos si la primera termina normalmente |

`&` con enteros opera sobre bits, no sobre condiciones booleanas.

```java
String texto = null;
if (texto != null && texto.length() > 0) {
    System.out.println(texto);
}
```

Cambiar && por & aquí evaluaría texto.length() y produciría [[Exception Handling|NullPointerException]].

Para [[Condicionales (Conditionals)|condiciones]], también existen `||` (O con cortocircuito) y `!` (negación). Negar un grupo requiere paréntesis: `!(a && b)`.

## Rangos y negaciones
Para que un valor esté dentro de un intervalo cerrado debe ser mayor o igual al mínimo **y** menor o igual al máximo. Para estar fuera basta con ser menor que el mínimo **o** mayor que el máximo. Exigir que sea simultáneamente menor que el mínimo y mayor que el máximo nunca detecta valores fuera de un intervalo ordinario.

Por De Morgan, `!(a && b)` equivale a `!a || !b`, y `!(a || b)` a `!a && !b`. Negar solo una parte cambia el significado. Con double o float, NaN no satisface las comparaciones de orden habituales; si el contrato exige un número finito, compruébalo además.

`>` excluye la igualdad y `>=` la incluye. Un límite máximo ya alcanzado y un mínimo exigido requieren razonar qué sucede exactamente en la frontera. El lenguaje admite ambas condiciones: el requisito determina cuál es correcta.

Fuente: [JLS §15.22–15.24](https://docs.oracle.com/javase/specs/jls/se25/html/jls-15.html).
