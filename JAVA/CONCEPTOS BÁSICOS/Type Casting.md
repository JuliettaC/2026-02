---
tags:
  - java
  - java/fundamentos
status: aprendido
aliases:
  - "Conversión de tipos (Type Casting)"
  - "casting"
---

# Type Casting
> [!summary] Qué es
> Convierte valores numéricos entre tipos compatibles, de forma implícita o mediante (tipo).

## Ampliación (widening)

- **Rutas implícitas:** byte → short → int → long → float → double.
- **Desde char:** char → int → long → float → double.
- short → char no es widening; no basta contar bits.

```java
int cantidad = 10;
double decimal = cantidad;
System.out.println(decimal);
```

> [!warning] Importante
> int → float y long → float/double pueden perder precisión aunque sean ampliaciones.

## Reducción (narrowing)

Puede perder rango o decimales; normalmente requiere un cast explícito.

```java
double precio = 19.99;
int precioEntero = (int) precio;
System.out.println(precioEntero); // 19: truncamiento hacia cero
```

## Error típico en promedios

```java
int suma = 17;
double incorrecto = suma / 3;
double correcto = (double) suma / 3;
System.out.println(incorrecto); // 5.0
System.out.println(correcto);  // 5.666...
```

**Recuerda:** convierte un operando **antes** de dividir. Castear el resultado no recupera los decimales descartados.

## Relacionado

[[Operadores aritméticos básicos|división]]

Fuente: [JLS §5.1.2–5.1.3](https://docs.oracle.com/javase/specs/jls/se25/html/jls-5.html).
