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

Fuente: [JLS §15.22–15.24](https://docs.oracle.com/javase/specs/jls/se25/html/jls-15.html).
