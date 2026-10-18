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
> [!summary] En una frase
> Las colecciones agrupan objetos; los genéricos expresan los tipos admitidos y permiten comprobar su uso al compilar.

## List y ArrayList
`List<E>` es una interfaz de secuencia ordenada que admite duplicados e índices desde cero. `ArrayList<E>` es una implementación redimensionable. No toda List admite agregar o quitar elementos: las capacidades dependen de la implementación. `List.of(...)` crea una lista no modificable y no admite elementos null. [[Array vs ArrayList]] conserva la comparación con arreglos.

`add` agrega, `get(i)` consulta una posición y `size()` cuenta elementos; no se usa `length` ni `length()`. En una lista de Integer, `remove(int)` elimina por índice mientras que `remove(Object)` busca por valor: la sobrecarga elegida importa. Recorrer con for-each permite consultar elementos sin administrar índices, pero modificar estructuralmente la misma lista durante ese recorrido puede fallar; para eliminar durante una iteración se necesita una operación compatible del iterador u otra estrategia apropiada.

## Genéricos y clases envolventes
`List<Alumno>` indica qué tipo de elementos acepta la lista; `Map<String, Alumno>` expresa tipos de clave y valor. El compilador puede rechazar usos incompatibles. Una variable Map no puede recibir un ArrayList: uno representa asociaciones y el otro una secuencia, aunque ambos agrupen datos.

Los parámetros de tipo requieren tipos de referencia: se usa Integer en lugar de int y Double en lugar de double. El autoboxing convierte valores primitivos a envolventes y el unboxing los extrae. Desempaquetar una referencia null causa NullPointerException. Un tipo sin parámetros (raw type) pierde garantías de tipos y puede desplazar el fallo a la ejecución.

`List<LibroImpreso>` no es subtipo de `List<Material>` aunque LibroImpreso herede de Material; permitir esa asignación dejaría introducir otros materiales en una lista de libros. No confundas la relación entre elementos con la relación entre tipos genéricos.

## Map y HashMap
Map asocia claves únicas con valores; no es un subtipo de Collection. HashMap es una implementación sin garantía de orden de recorrido. `put` agrega o reemplaza el valor de una clave, `get` consulta y `values()` ofrece una vista de los valores. Guardar por nombre y buscar por RUT, o guardar por título y buscar por código, rompe la regla de búsqueda aunque los tipos sean correctos.

Un `get` de HashMap puede devolver null si falta la clave o si la clave tiene asociado null. Usa `containsKey` cuando necesites distinguir esos casos. `getOrDefault` aporta un valor alternativo si no existe la clave, sin insertarlo.

`computeIfAbsent` recibe una función que construye el valor cuando la clave está ausente o asociada a null; no recibe directamente una lista. En `notas.computeIfAbsent(rut, clave -> new ArrayList<>()).add(evaluacion)`, la lambda recibe la clave y produce una lista solo cuando hace falta; después se agrega la evaluación a la lista obtenida. La expresión `->` representa aquí una función, no una asignación.

## Vistas y copias
`Collections.unmodifiableList(lista)` impide modificar a través de esa vista, pero los cambios realizados sobre la lista original siguen siendo visibles. `new ArrayList<>(lista)` crea una copia independiente de la estructura, que sigue siendo mutable. Envolver esa copia en una vista no modificable protege la estructura de la copia frente al receptor.

Son copias superficiales: los elementos siguen siendo referencias a los mismos objetos. Una lista no modificable no vuelve inmutables a sus alumnos ni préstamos. [[final]] tampoco impide modificar el contenido de una colección.

## ArrayDeque
ArrayDeque implementa una cola de dos extremos redimensionable. Permite agregar o retirar en ambos extremos y representar una cola FIFO o una pila LIFO. No admite null ni acceso por índice como List. Las operaciones de extracción pueden lanzar una excepción o devolver una señal de ausencia según el método elegido; esa diferencia forma parte del contrato.

Fuentes: [API java.util](https://docs.oracle.com/en/java/javase/25/docs/api/java.base/java/util/package-summary.html) y [JLS §4.5–4.8](https://docs.oracle.com/javase/specs/jls/se25/html/jls-4.html).
