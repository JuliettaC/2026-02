---
tags:
  - java
  - java/errores
status: documentado
---

# Tipos de errores
> [!summary] Qué es
> Un error puede impedir compilar, fallar al ejecutar o producir un resultado incorrecto.

## Error sintáctico: 
- **Qué es:** estructura que incumple la gramática por elementos ausentes, sobrantes o mal colocados.
- **Reconócelo:** el compilador pide un delimitador o una construcción válida; se detecta al compilar.

## Error léxico: 
- **Qué es:** caracteres, literales o escapes que no pueden formar componentes válidos del lenguaje.
- **Reconócelo:** el compilador señala escritura inválida; ocurre al procesar el texto fuente.

## Error semántico: 
- **Qué es:** estructura reconocible que incumple reglas de tipos, nombres, acceso o asignación.
- **Reconócelo:** el compilador rechaza su significado estático, aunque la puntuación sea correcta.

## Error de ejecución: 
- **Qué es:** una operación falla al encontrar datos, estados o recursos que impiden completarla.
- **Reconócelo:** aparece al ejecutar una ruta, normalmente mediante una excepción; no siempre termina la aplicación.

## Error lógico: 
- **Qué es:** el algoritmo no cumple el resultado esperado, aunque compile y termine sin excepciones.
- **Reconócelo:** compara resultados y estados con los requisitos; el compilador no conoce la intención del programa.

## Comparación rápida

| Tipo       | Problema principal               | Detección                            |
| ---------- | -------------------------------- | ------------------------------------ |
| Sintáctico | Estructura                       | Compilación                          |
| Léxico     | Formación de componentes         | Procesamiento del fuente             |
| Semántico  | Reglas estáticas                 | Compilación                          |
| Ejecución  | Operación que falla              | Al ejecutar                          |
| Lógico     | Resultado o conducta incorrectos | Revisión y pruebas contra requisitos |

## Importante
- Se conserva la clasificación de clase: **semántico** significa aquí semántica estática.
- Algunas etiquetas de las tablas originales son contradictorias: clasifica por la **regla infringida**.
- Una errata puede formar un nombre válido: no toda falta de escritura es léxica.
- Java admite concatenar texto y números; esa combinación no es siempre inválida.
- Un defecto lógico puede causar una excepción; distingue **causa** y **manifestación**.
- La clase **Error** de Java no engloba todos los errores de esta tabla.

## Relacionado

[[Exception Handling]] · [[Ciclo de vida de un programa en Java]] · [[Sintaxis básica]]

Fuentes: [JLS, estructura léxica](https://docs.oracle.com/javase/specs/jls/se25/html/jls-3.html), [reglas de nombres y acceso](https://docs.oracle.com/javase/specs/jls/se25/html/jls-6.html) y [excepciones](https://docs.oracle.com/javase/specs/jls/se25/html/jls-11.html). La separación didáctica en cinco tipos procede de tus apuntes de Lenguajes de Programación.
