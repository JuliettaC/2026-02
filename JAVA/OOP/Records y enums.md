---
tags:
  - java
  - java/oop
status: documentado
---

# Records y enums
> [!summary] Qué es
> Un record agrupa datos; un enum define un conjunto cerrado de opciones.

## Records

| Elemento | Qué recordar |
|---|---|
| Componentes | Generan campos private final y constructor canónico |
| Accesores | Nombre del componente con paréntesis: e.ponderacion() |
| Métodos generados | equals, hashCode y toString, salvo implementación explícita |
| Constructor compacto | Valida o normaliza antes de la asignación implícita |
| Herencia | Clase final; admite interfaces, no otra superclase explícita |

**Importante:**

- Métodos propios como aporte() también requieren paréntesis.
- **Inmutabilidad superficial:** no copia ni congela objetos mutables referenciados.
- Intercambiar argumentos del mismo tipo puede compilar y dar datos incorrectos.
- Nota fuera del rango: menor que el mínimo **o** mayor que el máximo. Valida NaN/infinito si el contrato los excluye.
- Records estables desde **Java 16**; el proyecto no declara versión objetivo.

## Enums

- **Qué es:** constantes de un tipo propio para opciones limitadas, como estados.
- Pueden tener campos, constructor y métodos.
- Permiten comprobar tipos, usar switch y comparar constantes con **==**.
- La regla de usar equals para contenido de String no se aplica igual a los enums.

Fuentes: [JLS §8.9 y §8.10](https://docs.oracle.com/javase/specs/jls/se25/html/jls-8.html).
