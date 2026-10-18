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
> [!summary] Qué es
> Una variable almacena un valor; su scope indica dónde puedes usar su nombre.

## Sintaxis

```java
int edad = 20;
edad = 21;
System.out.println(edad);
```

**Importante:** = asigna; == compara. El tipo limita lo asignable.

## Alcance de variables locales

Una local se usa desde su declaración dentro del bloque. Los bloques internos ven nombres externos, pero no al revés.

```java
int total = 10;
if (total > 0) {
    int descuento = 2;
    System.out.println(total - descuento);
}
// descuento no está disponible aquí.
```

> [!warning] Importante
> Scope es visibilidad del nombre, no destrucción inmediata del objeto. Fuera del bloque el nombre no existe: no «se vuelve null».

## Inicialización

| Variable | Valor inicial |
|---|---|
| Local | Debe asignarse antes de leerse |
| Campo / elemento de array | Valor por defecto: cero, false o null |
| Parámetro | Valor recibido al llamar |

## Recordatorio de clase: acumuladores

- **Total por boleta:** inicializa dentro del bucle de boletas.
- **Total general:** inicializa fuera.
- La ubicación depende de **qué quieres acumular**.

## Mantener el significado del estado

- Guardar siempre true **ignora** el argumento de asistencia.
- Contar !presente suma **ausencias**; corregir el contador no repara los datos mal guardados.
- Prestar → **prestado**; devolver → **disponible**.
- Un préstamo vigente debe distinguirse de uno cerrado.
- Un tipo correcto no garantiza un dato ni un resultado correcto.

## Relacionado

[[Tipos de datos|tipo]] · [[Tipos de errores#Error lógico: 2]] · [[Atributos y métodos#this|this]] · [[final]]

Fuentes: [JLS §6.3](https://docs.oracle.com/javase/specs/jls/se25/html/jls-6.html#jls-6.3) y [§4.12.5](https://docs.oracle.com/javase/specs/jls/se25/html/jls-4.html#jls-4.12.5).
