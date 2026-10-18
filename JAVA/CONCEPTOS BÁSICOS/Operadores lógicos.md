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
> [!summary] Qué es
> Combinan o niegan condiciones booleanas; el cortocircuito puede evitar una evaluación insegura.

## && frente a &

| Operador booleano | Cuándo evalúa la derecha |
|---|---|
| && | Solo si la izquierda es true |
| & | Siempre que la izquierda termine normalmente |
| \|\| | Solo si la izquierda es false |
| ! | Niega la condición |

```java
String texto = null;
if (texto != null && texto.length() > 0) {
    System.out.println(texto);
}
```

**Importante:** cambiar && por & puede causar NullPointerException. Con enteros, & opera sobre bits.

## Rangos y negaciones

| Intención | Condición |
|---|---|
| Dentro de [mínimo, máximo] | Mayor o igual al mínimo **y** menor o igual al máximo |
| Fuera del intervalo | Menor al mínimo **o** mayor al máximo |
| Negar a && b | !a \|\| !b |
| Negar a \|\| b | !a && !b |

- Niega grupos con paréntesis: **!(a && b)**.
- **>** excluye igualdad; **>=** la incluye. Revisa la frontera según el requisito.
- NaN no satisface comparaciones de orden: valida finitud si el contrato la exige.

## Relacionado

[[Exception Handling|NullPointerException]] · [[Condicionales (Conditionals)|condiciones]]

Fuente: [JLS §15.22–15.24](https://docs.oracle.com/javase/specs/jls/se25/html/jls-15.html).
