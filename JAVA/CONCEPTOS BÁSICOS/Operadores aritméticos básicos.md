---
tags:
  - java
  - java/fundamentos
status: aprendido
aliases:
  - "Math Operations"
---

# Operadores aritméticos básicos
> [!summary] Qué es
> Calculan valores; el tipo de los operandos determina cómo se realiza la operación.

| Operador | Uso |
|---|---|
| + / - / * | Sumar / restar / multiplicar |
| / | Dividir; entre enteros trunca hacia cero |
| % | Resto; también admite float/double |
| + con String | Concatenar |

## Ejemplo

**División:** 17 / 3 da **5**; 17 / 3.0 conserva decimales. El ejemplo completo está en [[Type Casting#Error típico en promedios]].

## Desbordamiento

```java
int arancel = 5_400_000;
int alumnos = 800;
long incorrecto = arancel * alumnos; // 25 032 704: desbordó como int
long correcto = (long) arancel * alumnos; // 4 320 000 000
System.out.println(incorrecto);
System.out.println(correcto);
```

**Importante:** convierte **antes de multiplicar**. El long receptor no repara un cálculo int desbordado; el resultado no siempre es negativo.

## Resto y errores comunes

- numero % 2 == 0 comprueba paridad; resto cero comprueba divisibilidad.
- Con negativos, el resto no garantiza un resultado positivo.
- División/resto **entero por cero:** ArithmeticException al ejecutar.
- División float/double por cero: puede producir **infinito o NaN**, sin esa excepción.

## Promoción, acumulación y asignación compuesta

| Regla | Qué recordar |
|---|---|
| byte, short, char | En aritmética habitual se promueven a int |
| Tipos mezclados | Predomina double, luego float, long e int |
| += | Incluye conversión al tipo de la variable izquierda |
| Acumular | += conserva lo anterior; = lo reemplaza |

- Un short en 32767 seguido de += 1 termina en **−32768**; la asignación simple de una suma int puede exigir cast.
- Para porcentajes con enteros, convierte **antes de dividir**.
- Define el caso sin datos y evita denominador cero.

## Math.round y límites

| Llamada | Retorno |
|---|---|
| Math.round(float) | int |
| Math.round(double) | long |
| Math.min / Math.max | Menor / mayor valor |
| Math.toIntExact(long) | int; falla si no cabe |

**Duda resuelta:** días long × tarifa int produce long. Conserva long en retorno y consumidores, o comprueba rango al reducir; otro cast a long no resuelve un retorno int.

## Relacionado

[[Type Casting]] · [[Exception Handling|ArithmeticException]] · [[Fechas con LocalDate]]

Fuente: [JLS §15.17 y §15.18](https://docs.oracle.com/javase/specs/jls/se25/html/jls-15.html).
