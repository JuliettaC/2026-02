---
tags:
  - java
  - java/fundamentos
status: aprendido
aliases:
  - "Naming Conventions"
---

# Convenciones de nombres
> [!summary] En una frase
> Nombres consistentes permiten reconocer clases, variables y métodos rápidamente.

| Elemento | Convención | Ejemplo |
|---|---|---|
| Clase | PascalCase | `MiClaseEjemplo` |
| Variable o método | camelCase | `nombreUsuario`, `calcularTotal()` |
| Constante | MAYÚSCULAS_CON_GUIONES | `VALOR_MAXIMO` |
| Package | minúsculas | `clases.ejemplos` |

Son convenciones, no requisitos generales del compilador. Lo obligatorio es respetar las reglas de identificadores de [[Sintaxis básica]].

El objeto no «tiene formato camelCase»: la variable que lo referencia suele usarlo. [[Clases y objetos]] distingue ambos conceptos. [[final]] explica qué significa impedir reasignación; no toda variable final se nombra como constante.

Fuente: [JLS §6.1](https://docs.oracle.com/javase/specs/jls/se25/html/jls-6.html#jls-6.1).
