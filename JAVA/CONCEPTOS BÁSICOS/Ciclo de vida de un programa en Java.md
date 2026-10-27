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
> [!summary] Qué es
> El fuente se compila a bytecode; una JVM compatible lo ejecuta.

## Consulta rápida

```text
Hola.java → javac → Hola.class → java / JVM → ejecución
```

```shell
javac Hola.java
java Hola
```

## Creación y compilación

| Elemento | Función |
|---|---|
| .java | Fuente |
| javac | Comprueba el lenguaje y genera uno o más .class |
| .class | Bytecode |

## Carga y preparación

| Etapa | Qué hace |
|---|---|
| Loading | Carga clases |
| Linking | Verifica, prepara campos static y resuelve referencias; la resolución puede diferirse |
| Initialization | Ejecuta inicializadores de clase |

## Ejecución y limpieza

- **HotSpot:** intérprete y JIT ejecutan y optimizan; no toda JVM usa la misma estrategia.
- **Garbage collector:** recupera objetos inalcanzables; retener referencias puede impedirlo.
- Terminar el proceso no garantiza ejecutar limpieza pendiente ni cerrar lógicamente recursos.
- **Portabilidad:** requiere JVM compatible y dependencias.

## Relación con los tipos de errores

**Compilar y ejecutar sin excepciones no demuestra corrección lógica:** hay que comprobar los requisitos.

## Relacionado

[[Sintaxis básica]] · [[static#Estado compartido e inicialización]] · [[static]] · [[Exception Handling]] · [[Tipos de errores]]

Fuente: [JLS §12](https://docs.oracle.com/javase/specs/jls/se25/html/jls-12.html).
