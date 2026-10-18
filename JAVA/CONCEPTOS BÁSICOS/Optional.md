---
tags:
  - java
  - java/fundamentos
status: documentado
---

# Optional
> [!summary] En una frase
> Optional representa explícitamente que una operación puede devolver un valor presente o ningún valor.

## Crear y consultar
`Optional<T>` contiene como máximo una referencia no nula de tipo T. `Optional.of(valor)` requiere un valor no null; si recibe null lanza NullPointerException. `Optional.ofNullable(valor)` permite ambos casos y produce un Optional vacío cuando recibe null. `Optional.empty()` expresa ausencia.

`isPresent()` comprueba presencia e `isEmpty()` ausencia. `get()` extrae el valor, pero lanza NoSuchElementException cuando está vacío. `orElse` proporciona una alternativa; `orElseGet` la calcula con una función solo si hace falta. `orElseThrow` permite tratar la ausencia como un fallo. `ifPresent` realiza una acción solo cuando hay contenido.

## Buscar en un repositorio
Si una búsqueda en Map puede devolver null, envolverla con of es incorrecto para el caso ausente. `Optional.ofNullable(datos.get(codigo))` permite que el servicio decida qué hacer cuando no hay material.

Si el repositorio devuelve `Optional<Material>`, llamar a `get()` produce Material, no otro Optional. Por eso asignar ese resultado a una variable Optional es una incompatibilidad de tipos. Primero conserva el resultado de la búsqueda y resuelve la ausencia; extrae el valor solo en una ruta donde haya presencia comprobada o mediante una operación que la gestione.

## Límites
Optional no garantiza que el contenido sea válido para el negocio ni evita todas las excepciones. Está pensado principalmente para retornos que expresan ausencia y una variable declarada Optional no debería ser null. Reemplaza la ambigüedad de una referencia ausente por un contrato explícito; no repara automáticamente un algoritmo.

Relacionado: [[Colecciones y genéricos]], [[Exception Handling]] y [[Herencia, interfaces y composición]].

Fuente: [API Optional](https://docs.oracle.com/en/java/javase/25/docs/api/java.base/java/util/Optional.html).
