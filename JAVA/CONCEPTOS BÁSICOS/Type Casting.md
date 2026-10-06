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
> [!summary] En una frase
> Convierte valores numéricos entre tipos compatibles, a veces automáticamente y a veces con `(tipo)`.

## Ampliación (widening)
Estas rutas habituales son implícitas:
- `byte → short → int → long → float → double`
- `char → int → long → float → double`

`short → char` no es widening. No basta con comparar el número de bits.

```java
int cantidad = 10;
double decimal = cantidad;
System.out.println(decimal);
```

> [!warning] Precisión
> Widening puede perder precisión: int→float y long→float/double no representan exactamente todos los enteros.

## Reducción (narrowing)
Puede perder decimales o rango y normalmente necesita un cast explícito.

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

Convierte un operando antes de la [[Operadores aritméticos básicos|división]]. Castear el resultado de una división entera no recupera los decimales.

Fuente: [JLS §5.1.2–5.1.3](https://docs.oracle.com/javase/specs/jls/se25/html/jls-5.html).
