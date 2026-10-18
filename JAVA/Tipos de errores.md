---
tags:
  - java
  - java/errores
status: documentado
---

# Tipos de errores
> [!summary] En una frase
> Un programa debe respetar el lenguaje, poder ejecutarse y cumplir su propósito; cada tipo de error señala un problema diferente.

## Error sintáctico:
**Qué es y por qué ocurre.** Es una infracción de la gramática: los componentes del programa no forman una estructura permitida. Surge al omitir, añadir o colocar incorrectamente delimitadores o partes obligatorias de una declaración o sentencia.

**Cómo se identifica y cuándo se detecta.** El análisis sintáctico del compilador no puede construir una estructura válida a partir de los tokens. El diagnóstico suele indicar un elemento esperado o una construcción incompleta. Se detecta durante la compilación. El lugar señalado puede estar después de la causa real; un defecto puede desencadenar varios mensajes.

**Diferencia.** El problema está en cómo se organizan los tokens. El léxico afecta su formación; el semántico afecta las reglas de significado de una estructura reconocible. Todavía no se está evaluando si el algoritmo resuelve correctamente el problema.

## Error léxico: 
**Qué es y por qué ocurre.** Impide reconocer correctamente los componentes elementales del código: identificadores, literales, operadores y separadores. Ocurre cuando los caracteres o su combinación incumplen las reglas de formación del lenguaje, incluidas las de escapes y literales.

**Cómo se identifica y cuándo se detecta.** El procesamiento del texto fuente no puede producir los elementos léxicos válidos esperados. El compilador informa de caracteres, escapes o literales inválidos, entre otros diagnósticos. Se detecta antes de ejecutar, durante el procesamiento del fuente; los escapes Unicode se procesan incluso antes de formar los tokens.

**Diferencia.** Se refiere a la escritura interna de los componentes, mientras que el sintáctico afecta su combinación. Una errata no es automáticamente léxica: puede formar otro identificador válido y fallar después por resolución de nombres.

## Error semántico: 
**Qué es y por qué ocurre.** En esta clasificación se refiere a una infracción de las reglas estáticas de significado: tipos incompatibles, nombres no resolubles, accesos no permitidos o incumplimiento de las condiciones exigidas por una declaración. Una estructura gramaticalmente reconocible no garantiza que sus operaciones sean válidas.

**Cómo se identifica y cuándo se detecta.** El compilador relaciona los nombres con sus declaraciones, verifica tipos, accesibilidad y reglas de asignación, y rechaza el programa si no se cumplen. Se detecta en compilación, aunque el código parezca bien puntuado.

**Diferencia.** A diferencia del error sintáctico, la estructura puede reconocerse. A diferencia del lógico, existe una regla del lenguaje que permite rechazarla sin conocer la intención del autor. «Semántico» puede abarcar también comportamiento en otros enfoques teóricos; aquí se usa el sentido estático para mantener separada la categoría de errores lógicos de clase.

## Error de ejecución: 
**Qué es y por qué ocurre.** Es un fallo que se manifiesta mientras el programa está funcionando, porque una operación encuentra un estado, dato, recurso o condición que impide completarla normalmente. La compilación no comprueba todos los valores ni todas las circunstancias del entorno.

**Cómo se identifica y cuándo se detecta.** Se observa al ejecutar una ruta afectada, mediante excepciones, trazas de llamadas o fallos de la JVM. Puede depender de una entrada concreta y permanecer oculto en otras ejecuciones. Se detecta durante la ejecución, no por el mero hecho de compilar.

**Diferencia.** Interrumpe una operación y altera su flujo normal; un error lógico puede completar las operaciones con resultados equivocados. Un fallo de ejecución no siempre termina toda la aplicación: puede manejarse o afectar a un hilo. La categoría tampoco coincide exclusivamente con la clase Error de Java; véase [[Exception Handling]].

## Error lógico: 
**Qué es y por qué ocurre.** Es una discrepancia entre el comportamiento del programa y el resultado que exige el problema. Ocurre cuando el algoritmo, las condiciones, el estado compartido, el orden de las operaciones o la interpretación de los requisitos son incorrectos, aunque todas las operaciones sean legales.

**Cómo se identifica.** Es necesario contrastar lo que hace el programa con un resultado esperado independiente. Ayudan la revisión del razonamiento, el seguimiento de los cambios de estado y las pruebas de casos normales, límites y situaciones alternativas. Un resultado verosímil no demuestra que sea correcto. Sin requisitos suficientes, no siempre es posible decidir si una conducta es un error o una decisión intencional.

**Cuándo se detecta.** Puede descubrirse al revisar el diseño o el código, durante pruebas o después de utilizar el sistema. El compilador comprueba reglas del lenguaje; normalmente no conoce las reglas del problema ni puede deducir la intención del autor. Por eso un programa puede compilar, ejecutar todas sus instrucciones y terminar normalmente, pero entregar resultados incorrectos. Que no se lance una excepción solo indica que no se notificó ese tipo de fallo, no que se cumplió el objetivo.

**Diferencia.** Su criterio de corrección es el propósito del programa, no la gramática ni la compatibilidad de tipos. Tampoco requiere una interrupción de ejecución. Un defecto de lógica puede provocar a su vez una excepción: la causa y su manifestación pertenecen a niveles diferentes y conviene explicar ambas.

## Relación con las anotaciones de clase
Las tablas del 7 y 14 de octubre contienen etiquetas provisionales que no siempre coinciden con las definiciones que las acompañan. La clasificación depende de la regla infringida, no solo de cómo redacta el compilador su mensaje. La ausencia de un delimitador es sintáctica; la formación inválida de un literal es léxica; la resolución o compatibilidad de nombres y tipos corresponde a semántica estática. Se conservan los originales como registro, sin adoptar sus contradicciones como reglas de Java.

Tampoco toda operación que combina texto y números es semánticamente inválida: Java admite concatenación. Una diferencia entre contenido textual y el requisito puede ser lógica aunque la operación sea legal. En Java, los errores de compilación engloban más de una de estas categorías y la jerarquía de excepciones clasifica objetos lanzables, no todos los defectos de un programa.

## Relacionado
- [[Ciclo de vida de un programa en Java]]: compilación y ejecución.
- [[Exception Handling]]: propagación y manejo de fallos.
- [[Sintaxis básica]]: escritura del lenguaje.

Fuentes: [JLS, estructura léxica](https://docs.oracle.com/javase/specs/jls/se25/html/jls-3.html), [reglas de nombres y acceso](https://docs.oracle.com/javase/specs/jls/se25/html/jls-6.html) y [excepciones](https://docs.oracle.com/javase/specs/jls/se25/html/jls-11.html). La separación didáctica en cinco tipos procede de tus apuntes de Lenguajes de Programación.
