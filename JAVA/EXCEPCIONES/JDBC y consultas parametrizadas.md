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
> [!summary] En una frase
> JDBC conecta Java con una base de datos; las consultas parametrizadas separan los datos de la estructura SQL y las transacciones coordinan cambios relacionados.

## Connection, PreparedStatement y ResultSet
Connection representa una conexión. PreparedStatement prepara una sentencia con parámetros de datos y ResultSet permite recorrer el resultado de una consulta. `executeQuery()` devuelve filas y `executeUpdate()` realiza operaciones de modificación y devuelve un recuento. El cursor de ResultSet empieza antes de la primera fila; `next()` avanza e indica si existe una fila para leer.

Los índices de parámetros comienzan en 1. El SQL `WHERE rut = ?` se acompaña de `setString(1, rut)`. El signo de interrogación no debe quedar entre comillas SQL. Preparar una sentencia que ya concatena la entrada no la vuelve segura ni crea parámetros que puedan asignarse después.

## Inyección SQL
Ocurre cuando datos externos se integran como parte de la estructura ejecutable de la consulta. No es exclusiva de aplicaciones web: también puede afectar a una aplicación de escritorio. Enlazar valores mediante parámetros evita interpretarlos como instrucciones SQL dentro de esas posiciones de datos.

Los parámetros no sustituyen libremente nombres de tablas, columnas ni palabras de ordenamiento. Si esa estructura debe variar, se elige entre opciones permitidas y se construye por separado. Validar datos ayuda al modelo, pero no reemplaza la parametrización.

## Cierre de recursos
El try-with-resources declara recursos AutoCloseable y los cierra automáticamente en orden inverso al de declaración, también al salir por excepción. En los apuntes, el bloque externo cierra PreparedStatement y el interno cierra ResultSet. No cierra una conexión recibida desde fuera que no se declaró como recurso allí: su propietario debe definir su ciclo de vida.

Cerrar recursos no equivale a capturar la excepción. SQLException puede propagarse con throws; consulta [[Exception Handling#throw y throws]]. Si fallan tanto el cuerpo como el cierre, la excepción del cierre puede quedar suprimida y asociada a la principal.

## Transacciones
Con autoCommit desactivado, varias modificaciones pueden confirmarse conjuntamente mediante commit. Ante un fallo, rollback intenta deshacer los cambios de la transacción. En los apuntes, registrar un préstamo y marcar el material deben mantener coherencia; confirmar solo una parte dejaría un estado incorrecto.

El patrón mostrado necesita un contrato de propiedad: debe saberse si el método administra la transacción o participa en otra ya iniciada. No se debe confirmar ni revertir indiscriminadamente trabajo ajeno. Si el método cambia autoCommit en una conexión reutilizada, debe restaurar el estado según ese contrato al finalizar y manejar también posibles fallos del rollback sin perder el diagnóstico original. Un cierre automático por sí solo no sustituye commit o rollback.

## Límites del material disponible
Los fragmentos no incluyen esquema completo, controlador JDBC, configuración de conexión ni requisitos de concurrencia. Permiten explicar el mecanismo, pero no comprobar las consultas contra una base real ni garantizar una transacción correcta para un sistema completo.

Fuentes: [Oracle: consultas parametrizadas](https://docs.oracle.com/javase/tutorial/jdbc/basics/prepared.html), [Connection](https://docs.oracle.com/en/java/javase/25/docs/api/java.sql/java/sql/Connection.html) y [JLS §14.20.3](https://docs.oracle.com/javase/specs/jls/se25/html/jls-14.html#jls-14.20.3).
