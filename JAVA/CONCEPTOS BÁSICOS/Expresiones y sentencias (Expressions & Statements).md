---
tags:
  - java
  - java/fundamentos
status: aprendido
aliases:
  - "Expressions & Statements"
---

# Expresiones y sentencias
> [!summary] En una frase
> Una expresión describe un cálculo o evaluación; una sentencia determina una acción o control de ejecución.

## Ejemplo
```java
int resultado = 5 + 3;
System.out.println(resultado);
if (resultado > 5) {
    System.out.println("Es mayor que 5");
}
```

- `5 + 3` produce int; `resultado > 5` produce boolean.
- `int resultado = 5 + 3;` es una declaración local con inicialización, no `int= resultado = ...`.
- `System.out.println(resultado);` es una sentencia de expresión; su llamada devuelve void.
- No toda expresión produce un valor utilizable: una llamada void no lo hace.
- No toda sentencia termina en `;`: [[Condicionales (Conditionals)|if]] y bloques usan su propia estructura.

[[Operadores aritméticos básicos]] y [[Operadores lógicos]] construyen expresiones; [[Sintaxis básica]] explica sus delimitadores.

Fuentes: [JLS §15.1](https://docs.oracle.com/javase/specs/jls/se25/html/jls-15.html#jls-15.1) y [§14](https://docs.oracle.com/javase/specs/jls/se25/html/jls-14.html).
