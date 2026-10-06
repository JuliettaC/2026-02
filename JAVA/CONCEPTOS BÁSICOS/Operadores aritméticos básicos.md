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

Fuente: [JLS §15.17 y §15.18](https://docs.oracle.com/javase/specs/jls/se25/html/jls-15.html).
