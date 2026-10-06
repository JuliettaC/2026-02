---
tags:
  - java
  - java/fundamentos
status: aprendido
aliases:
  - "Lifecycle of a Program"
  - "JVM"
  - "javac"
---

# Ciclo de vida de un programa en Java
> [!summary] En una frase
> El código fuente se compila a bytecode y una JVM compatible lo ejecuta.

## Consulta rápida
```text
Hola.java → javac → Hola.class → java / JVM → ejecución
```

Para el ejemplo completo de [[Sintaxis básica]]:
```shell
javac Hola.java
java Hola
```

## Creación y compilación
- `.java`: fuente escrito por el programador.
- `javac`: comprueba sintaxis y tipos y genera uno o más `.class` con bytecode.
- Un error de compilación impide generar correctamente el programa; que compile no garantiza que haga lo esperado.

## Carga y preparación
Detalle conservado de clase:
- **Loading:** la JVM carga la representación binaria de las clases.
- **Linking:** verifica bytecode, prepara campos static con valores por defecto y resuelve referencias simbólicas. La resolución puede ser diferida.
- **Initialization:** ejecuta la inicialización de clase, incluidos inicializadores static. Solo se conserva esta mención; los bloques inicializadores quedan pendientes.

## Ejecución y limpieza
- En JVM como HotSpot, el intérprete y el JIT permiten ejecutar y optimizar bytecode frecuente; no toda JVM debe usar exactamente esa estrategia.
- El garbage collector recupera memoria de objetos que ya no son alcanzables. No impide todas las fugas: una referencia retenida innecesariamente puede impedir recuperar memoria.
- Al terminar el proceso, el sistema operativo recupera sus recursos; esto no garantiza ejecutar toda limpieza pendiente ni cerrar lógicamente cada recurso.
- «Write once, run anywhere» requiere una JVM compatible y las dependencias del programa.

[[static]] ayuda a distinguir inicialización de clase de la preparación de cada objeto. Los fallos durante ejecución se consultan en [[Exception Handling]].

Fuente: [JLS §12](https://docs.oracle.com/javase/specs/jls/se25/html/jls-12.html).
