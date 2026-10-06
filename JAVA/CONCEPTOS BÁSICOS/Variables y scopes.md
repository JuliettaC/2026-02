---
tags:
  - java
  - java/fundamentos
status: aprendido
aliases:
  - "El alcance en bloques de código"
  - "Variables"
  - "scope"
  - "Variables and Scopes"
---

# Variables y scopes
> [!summary] En una frase
> Una variable almacena un valor; su scope determina dónde puedes referirte a ella por su nombre.

## Sintaxis
```java
int edad = 20;
edad = 21;
System.out.println(edad);
```

El [[Tipos de datos|tipo]] limita lo que puedes asignar. `=` asigna; `==` compara.

## Alcance de variables locales
Desde su declaración, una variable local puede usarse dentro de su bloque. Un bloque interno puede usar variables externas; el externo no ve las declaradas dentro.

```java
int total = 10;
if (total > 0) {
    int descuento = 2;
    System.out.println(total - descuento);
}
// descuento no está disponible aquí.
```

> [!warning] Confusión frecuente
> Salir del scope no garantiza destrucción inmediata de memoria ni de un objeto referenciado. Scope trata de visibilidad del nombre.

## Inicialización
- Las locales deben estar asignadas antes de leerlas.
- Los campos y los elementos de arrays reciben valores por defecto: `0`, `false` o `null`, según el tipo.
- Los parámetros reciben el valor proporcionado al llamar al método.
- Un nombre no disponible fuera del bloque causa error de compilación; no «se vuelve null».

## Recordatorio de clase: acumuladores
Si quieres un total por boleta, inicializa el acumulador dentro del bucle de boletas. Si quieres un total general, colócalo fuera. La ubicación depende del cálculo, no de una regla única.

Cuando un parámetro tiene el mismo nombre que un campo, usa [[Atributos y métodos#this|this]] para distinguirlos. [[final]] restringe la reasignación.

Fuentes: [JLS §6.3](https://docs.oracle.com/javase/specs/jls/se25/html/jls-6.html#jls-6.3) y [§4.12.5](https://docs.oracle.com/javase/specs/jls/se25/html/jls-4.html#jls-4.12.5).
