---
tags:
  - java
  - java/fundamentos
status: aprendido
aliases:
  - "Expressions & Statements"
---

# Expresiones y sentencias
> [!summary] Qué es
> Una expresión evalúa un cálculo; una sentencia realiza una acción o controla el flujo.

## Ejemplo

```java
int resultado = 5 + 3;
System.out.println(resultado);
if (resultado > 5) {
    System.out.println("Es mayor que 5");
}
```

| Fragmento | Qué representa |
|---|---|
| 5 + 3 | Expresión de tipo int |
| resultado > 5 | Expresión de tipo boolean |
| int resultado = 5 + 3; | Declaración local con inicialización |
| System.out.println(resultado); | Sentencia de expresión con llamada void |
| if (...) { ... } | Control condicional |

**Importante:** una llamada void no produce un valor utilizable. No toda sentencia termina en punto y coma.

## Relacionado

[[Condicionales (Conditionals)|if]] · [[Operadores aritméticos básicos]] · [[Operadores lógicos]] · [[Sintaxis básica]]

Fuentes: [JLS §15.1](https://docs.oracle.com/javase/specs/jls/se25/html/jls-15.html#jls-15.1) y [§14](https://docs.oracle.com/javase/specs/jls/se25/html/jls-14.html).
