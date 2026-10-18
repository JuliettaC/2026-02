---
tags:
  - java
  - java/fundamentos
status: documentado
---

# Fechas con LocalDate
> [!summary] En una frase
> LocalDate representa una fecha de calendario sin hora ni zona horaria y permite calcular vencimientos y diferencias de días.

## Construcción y operaciones
`LocalDate.of(año, mes, día)` valida una fecha; un día inexistente produce DateTimeException. Los meses usan números de 1 a 12. `plusDays(n)` devuelve otra fecha y conserva la original: LocalDate es inmutable. La fecha de vencimiento de un préstamo puede obtenerse sumando su duración al día de retiro.

`ChronoUnit.DAYS.between(inicio, fin)` devuelve un long con los días entre las fechas y puede ser negativo si fin es anterior a inicio. El orden de los argumentos importa. No expresa horas transcurridas ni aplica una zona horaria.

## Días de atraso y multas
Si el atraso solo debe contar después del vencimiento, calcula la diferencia desde el vencimiento hasta la fecha relevante y limita inferiormente a cero con `Math.max(0, dias)`. `Math.min(0, dias)` conserva anticipos negativos y convierte los atrasos positivos en cero: es la operación opuesta al requisito.

La fecha relevante depende del estado del préstamo. Si ya se devolvió, calcular siempre hasta la fecha del informe podría seguir aumentando una multa cerrada. Debe definirse si se usa la devolución efectiva o la fecha de consulta, y si la regla permite multas negativas, días de gracia o cambios de tarifa. Los fragmentos no especifican todas esas políticas.

La multiplicación por una tarifa int conserva long; [[Operadores aritméticos básicos]] explica la conversión al retornar. Elegir correctamente el tipo no sustituye la definición de la regla de negocio.

Fuente: [API LocalDate](https://docs.oracle.com/en/java/javase/25/docs/api/java.base/java/time/LocalDate.html) y [ChronoUnit](https://docs.oracle.com/en/java/javase/25/docs/api/java.base/java/time/temporal/ChronoUnit.html).
