---
tags:
  - java
  - java/fundamentos
status: documentado
---

# Fechas con LocalDate
> [!summary] Qué es
> Representa una fecha sin hora ni zona horaria; sirve para vencimientos y diferencias de días.

## Construcción y operaciones

| Operación | Resultado |
|---|---|
| LocalDate.of(año, mes, día) | Fecha válida; mes entre 1 y 12 |
| plusDays(n) | Nueva fecha; no modifica la original |
| ChronoUnit.DAYS.between(inicio, fin) | Días como long; negativo si fin es anterior |

**Importante:** una fecha inexistente causa DateTimeException. Estos días no son horas transcurridas ni aplican zonas horarias.

## Días de atraso y multas

- Diferencia: **vencimiento → fecha relevante**.
- Atraso no negativo: **Math.max(0, dias)**.
- Math.min hace lo contrario: conserva negativos y elimina atrasos positivos.
- Préstamo cerrado: usa la **devolución efectiva** si así lo exige la regla; la fecha del informe podría seguir aumentando la multa.
- Días long × tarifa int produce **long**; reducir a int exige comprobar rango.
- Días de gracia y cambios de tarifa necesitan requisitos: no están completos en los fragmentos.

## Relacionado

[[Operadores aritméticos básicos]]

Fuente: [API LocalDate](https://docs.oracle.com/en/java/javase/25/docs/api/java.base/java/time/LocalDate.html) y [ChronoUnit](https://docs.oracle.com/en/java/javase/25/docs/api/java.base/java/time/temporal/ChronoUnit.html).
