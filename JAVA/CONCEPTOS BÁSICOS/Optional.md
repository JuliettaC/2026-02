---
tags:
  - java
  - java/fundamentos
status: documentado
---

# Optional
> [!summary] Qué es
> Representa un resultado que puede contener un valor o estar vacío.

## Crear y consultar

| Operación | Qué hace |
|---|---|
| of(valor) | Exige no null; si recibe null, falla |
| ofNullable(valor) | null se convierte en vacío |
| empty() | Crea un Optional vacío |
| isPresent() / isEmpty() | Comprueba presencia / ausencia |
| get() | Extrae; vacío causa NoSuchElementException |
| orElse(alternativa) | Usa la alternativa si está vacío |
| orElseGet(función) | Calcula la alternativa solo si hace falta |
| orElseThrow() | Lanza si está vacío |
| ifPresent(acción) | Actúa solo cuando hay valor |

## Buscar en un repositorio

- Un Map puede devolver null: envuelve la búsqueda con **ofNullable**, no of.
- Si recibes Optional<Material>, **get() devuelve Material**, no otro Optional.
- Resuelve la ausencia antes de extraer: comprueba presencia o usa las operaciones de la tabla.

## Límites

- Se usa principalmente en **retornos que admiten ausencia**.
- Una variable Optional no debería ser null.
- No valida reglas del negocio ni evita todas las excepciones.

## Relacionado

[[Colecciones y genéricos]] · [[Exception Handling]] · [[Herencia, interfaces y composición]]

Fuente: [API Optional](https://docs.oracle.com/en/java/javase/25/docs/api/java.base/java/util/Optional.html).
