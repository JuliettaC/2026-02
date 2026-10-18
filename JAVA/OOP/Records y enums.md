---
tags:
  - java
  - java/oop
status: documentado
---

# Records y enums
> [!summary] En una frase
> Un record modela un conjunto de datos; un enum representa un conjunto cerrado de constantes con nombre.

## Records
Un record declara componentes a partir de los cuales Java genera campos privados final, un constructor canónico, accesores, equals, hashCode y toString. Sus accesores tienen el nombre del componente y paréntesis: `e.ponderacion()`. No son campos públicos ni usan necesariamente el prefijo get.

El constructor compacto permite validar o normalizar los parámetros antes de la asignación implícita a los campos. En Evaluacion, la condición de nota fuera del intervalo debe detectar estar por debajo del mínimo **o** por encima del máximo; exigir ambas cosas a la vez impide detectar esos valores. Si el contrato excluye NaN o infinito, esa condición requiere validación adicional.

Los records son clases implícitamente final; pueden implementar interfaces y declarar métodos de cálculo, pero no extender otra clase explícitamente. Un método como `aporte()` sigue siendo un método: se invoca con paréntesis.

La inmutabilidad es superficial: si un componente referencia una lista mutable, sus elementos pueden cambiar. El record no crea automáticamente copias defensivas. Un record con varios componentes del mismo tipo puede construirse con argumentos intercambiados y compilar: respetar su significado sigue siendo responsabilidad del autor.

## Enums
Un enum declara constantes de un tipo propio para un conjunto cerrado de opciones, como estados o categorías. Puede tener campos, constructor y métodos. Evita representar opciones limitadas mediante textos arbitrarios y permite que el compilador compruebe el tipo. Sus constantes pueden compararse con `==` y utilizarse en switch; no se aplica la recomendación de usar equals para contenido de String a todos los tipos por igual.

Los records son una característica estable desde Java 16; el proyecto no declara una versión objetivo, por lo que conviene comprobarla antes de convertir los fragmentos de clase en una aplicación.

Fuentes: [JLS §8.9 y §8.10](https://docs.oracle.com/javase/specs/jls/se25/html/jls-8.html).
