---
tags:
  - java
  - java/fundamentos
status: documentado
aliases:
  - "Collections"
  - "List"
  - "Map"
  - "ArrayDeque"
---

# Colecciones y genéricos
> [!summary] Qué es
> Agrupan objetos; los genéricos indican qué tipos admite cada estructura.

## List y ArrayList

| Concepto | Qué recordar |
|---|---|
| List | Secuencia con índices desde cero; admite duplicados |
| ArrayList | Implementación redimensionable de List |
| List.of(...) | Lista no modificable; rechaza null |
| add / get(i) / size() | Agregar / consultar / contar |
| remove(int) / remove(Object) | Eliminar por índice / por valor |

**Importante:** no toda List admite cambios. Evita modificaciones estructurales durante for-each; usa un iterador compatible u otra estrategia.

## Genéricos y clases envolventes

- **List<Alumno>:** elementos Alumno; **Map<String, Alumno>:** claves String y valores Alumno.
- Los parámetros de tipo usan referencias: **Integer**, no int; **Double**, no double. String no es un envolvente de un primitivo.
- **Boxing:** primitivo → envolvente. **Unboxing:** envolvente → primitivo; null produce NullPointerException.
- **Raw type:** omite los parámetros y pierde comprobaciones de tipos.
- List<LibroImpreso> **no** es subtipo de List<Material>, aunque sus elementos tengan esa relación.
- Un ArrayList **no** es un Map: representan estructuras diferentes.

## Map y HashMap

**Qué es:** Map asocia claves únicas con valores; no hereda de Collection. HashMap no garantiza orden de recorrido.

| Operación | Función |
|---|---|
| put(clave, valor) | Agrega o reemplaza |
| get(clave) | Consulta; HashMap puede devolver null |
| containsKey(clave) | Distingue clave ausente de valor null |
| values() | Vista de los valores |
| getOrDefault(clave, alternativa) | Devuelve alternativa si falta la clave; no la inserta |
| computeIfAbsent | Calcula un valor si falta o está asociado a null |

**Duda resuelta:** guarda y busca con la misma clave: RUT con RUT, código con código.

**Lambda:** en notas.computeIfAbsent(rut, clave -> new ArrayList<>()).add(evaluacion), la función crea la lista cuando hace falta; después se agrega la evaluación. El método espera una **función**, no una lista.

## Vistas y copias

| Operación | Resultado |
|---|---|
| Collections.unmodifiableList(lista) | Vista no modificable; refleja cambios del original |
| new ArrayList<>(lista) | Copia mutable de la estructura |
| Vista no modificable de una copia | Estructura independiente que el receptor no puede modificar |

**Importante:** las copias son superficiales: comparten los objetos. Ni una vista ni final vuelven inmutables los elementos.

## ArrayDeque

- **Qué es:** cola redimensionable de dos extremos; permite FIFO o pila LIFO.
- No admite null ni acceso por índice.
- Según el método, extraer sin elementos devuelve una señal de ausencia o lanza una excepción.

## Relacionado

[[Array vs ArrayList]] · [[final]]

Fuentes: [API java.util](https://docs.oracle.com/en/java/javase/25/docs/api/java.base/java/util/package-summary.html) y [JLS §4.5–4.8](https://docs.oracle.com/javase/specs/jls/se25/html/jls-4.html).
