---
tags:
  - java
  - java/fundamentos
status: aprendido
aliases:
  - "Math Operations"
---

# Operadores aritméticos básicos
> [!summary] En una frase
> +, -, *, / y % realizan cálculos; el tipo de los operandos determina cómo se calcula.

| Operador | Uso |
|---|---|
| `+` | Suma; con String también concatena |
| `-` | Resta |
| `*` | Multiplica |
| `/` | Divide; entre enteros trunca hacia cero |
| `%` | Resto de división; también admite float/double |

## Ejemplo
```java
int suma = 17;
double sinDecimales = suma / 3; // 5.0
double promedio = suma / 3.0;  // 5.666...
boolean esPar = suma % 2 == 0;
System.out.println(promedio);
System.out.println(esPar); // false
```

El tipo de la variable receptora no vuelve decimal una división entera. Consulta [[Type Casting]] para convertir antes de calcular.

## Desbordamiento
```java
int arancel = 5_400_000;
int alumnos = 800;
long incorrecto = arancel * alumnos; // 25 032 704: desbordó como int
long correcto = (long) arancel * alumnos; // 4 320 000 000
System.out.println(incorrecto);
System.out.println(correcto);
```

Un overflow no siempre produce negativo. En cálculos simples con estos operandos, convierte antes de multiplicar; el `long` de la izquierda no repara la cuenta.

## Resto y errores comunes
- `numero % 2 == 0` comprueba paridad; `numero % divisor == 0` comprueba divisibilidad.
- El resto puede ayudar a repetir posiciones; con negativos no garantiza un resultado positivo.
- La división o resto entero por cero lanza [[Exception Handling|ArithmeticException]].
- Con float/double, dividir por cero puede producir infinito o NaN, sin esa excepción.

## Promoción, acumulación y asignación compuesta
En las operaciones aritméticas habituales, byte, short y char se promueven a int. Si participa un double el cálculo se hace como double; si no, float prevalece sobre long y long sobre int. Convertir un resultado ya desbordado no recupera su valor original.

`+=` combina cálculo y conversión implícita al tipo de la variable izquierda. Por eso un short en 32767 seguido de `+= 1` compila y termina en −32768; una asignación simple de una suma int a short puede exigir conversión explícita. Que compile no garantiza conservar el rango.

Acumular requiere conservar lo anterior: `ponderacion += e.ponderacion()` suma todas las ponderaciones; `ponderacion = e.ponderacion()` deja solo la última. Para un porcentaje con contadores enteros, convierte antes de dividir. Debes definir también qué resultado representa la ausencia de datos y evitar un denominador cero. Son decisiones del cálculo, no simples cambios de sintaxis.

## Math.round y límites
`Math.round(float)` devuelve int y `Math.round(double)` devuelve long. Si `neto * TASA_IVA` produce double, asignar el resultado de round directamente a int no es válido. Mantener long suele evitar una reducción innecesaria; si el contrato exige int, comprueba rango y usa una conversión adecuada. Un cast a long de un resultado que ya es long no lo hace compatible con un retorno int.

En el cálculo de multas del 7 de octubre, multiplicar días long por una tarifa int produce long. Puede conservarse long en el retorno y sus consumidores; reducir a int exige comprobar el rango, por ejemplo con Math.toIntExact. Castear a long, como propone la tabla original, no resuelve esa incompatibilidad.

`Math.min` elige el menor y `Math.max` el mayor; escoger uno u otro debe responder al significado del cálculo. [[Fechas con LocalDate]] relaciona esto con los días de atraso.

Fuente: [JLS §15.17 y §15.18](https://docs.oracle.com/javase/specs/jls/se25/html/jls-15.html).
