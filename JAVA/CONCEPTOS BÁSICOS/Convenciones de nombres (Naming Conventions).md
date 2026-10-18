---
tags:
  - java
  - java/fundamentos
status: aprendido
aliases:
  - "Naming Conventions"
---

# Convenciones de nombres
> [!summary] Qué es
> Son pautas para reconocer clases, variables y métodos al leer.

| Elemento | Convención | Ejemplo |
|---|---|---|
| Clase | PascalCase | MiClase |
| Variable / método | camelCase | nombreUsuario / calcularTotal() |
| Constante | MAYÚSCULAS_CON_GUIONES | VALOR_MAXIMO |
| Package | minúsculas | clases.ejemplos |

## Importante

- Son **convenciones**, no requisitos generales del compilador.
- Debes respetar las reglas de **identificadores**.
- camelCase describe el nombre de la variable, no el objeto.
- No toda variable final se nombra como una constante.

## Relacionado

[[Sintaxis básica]] · [[Clases y objetos]] · [[final]]

Fuente: [JLS §6.1](https://docs.oracle.com/javase/specs/jls/se25/html/jls-6.html#jls-6.1).
