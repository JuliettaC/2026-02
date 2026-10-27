---
tags:
  - java
  - java/excepciones
status: documentado
aliases:
  - "JDBC"
  - "SQL injection"
---

# JDBC y consultas parametrizadas
> [!summary] Qué es
> JDBC conecta Java con bases de datos; parámetros y transacciones ayudan a ejecutar operaciones coherentes.

## Connection, PreparedStatement y ResultSet

| Elemento | Función |
|---|---|
| Connection | Conexión con la base |
| PreparedStatement | Sentencia con parámetros de datos |
| ResultSet | Filas devueltas por una consulta |
| executeQuery() | Devuelve un ResultSet |
| executeUpdate() | Modifica y devuelve el número de filas afectadas |
| next() | Avanza desde antes de la primera fila |

**Parámetros:** WHERE rut = ? se acompaña de setString(1, rut). Empiezan en **1** y el signo ? va sin comillas SQL.

## Inyección SQL

- **Qué es:** datos externos pasan a formar parte del código SQL; también afecta aplicaciones de escritorio.
- **Cómo evitarla en valores:** parámetros, sin concatenar la entrada.
- Preparar una consulta ya concatenada **no** la vuelve segura.
- Tablas, columnas y ordenamiento variables requieren **opciones permitidas**, no parámetros de valores.
- Validar entrada no reemplaza parametrizar.

## Cierre de recursos

- **Try-with-resources:** cierra recursos AutoCloseable en orden inverso, incluso ante excepciones.
- Cierra solo los recursos declarados: no una Connection externa ajena al bloque.
- Cerrar no significa capturar; SQLException puede propagarse con throws.
- Si fallan cuerpo y cierre, la excepción de cierre puede quedar **suprimida** en la principal.

## Transacciones

| Operación | Efecto |
|---|---|
| setAutoCommit(false) | Permite agrupar cambios |
| commit() | Confirma la transacción |
| rollback() | Intenta deshacerla ante un fallo |

**Importante:**

- Registrar el préstamo y marcar el material deben mantener coherencia.
- Define **quién administra la transacción**: no confirmes ni reviertas trabajo ajeno.
- En conexiones reutilizadas, restaura autoCommit según ese contrato.
- Un fallo del rollback no debe ocultar el fallo original.
- Cerrar recursos no sustituye commit o rollback.

## Límites del material disponible

Faltan esquema completo, controlador, conexión y reglas de concurrencia; no se verificaron consultas contra una base real.

## Relacionado

[[Exception Handling#throw y throws]]

Fuentes: [Oracle: consultas parametrizadas](https://docs.oracle.com/javase/tutorial/jdbc/basics/prepared.html), [Connection](https://docs.oracle.com/en/java/javase/25/docs/api/java.sql/java/sql/Connection.html) y [JLS §14.20.3](https://docs.oracle.com/javase/specs/jls/se25/html/jls-14.html#jls-14.20.3).
