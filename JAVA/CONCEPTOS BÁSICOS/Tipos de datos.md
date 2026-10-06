---
tags:
  - java
  - java/fundamentos
status: aprendido
aliases:
  - "Tipo de datos"
  - "Data Types"
---

# Tipos de datos

> [!summary] En una frase
> El tipo determina los valores y operaciones permitidos; una variable guarda un valor primitivo o una referencia.

## Primitivos
| Tipo      | Recordatorio                                                    |
| --------- | --------------------------------------------------------------- |
| `byte`    | 8 bits; −128 a 127                                              |
| `short`   | 16 bits; −32 768 a 32 767                                       |
| `int`     | 32 bits; −2 147 483 648 a 2 147 483 647                         |
| `long`    | 64 bits; −9 223 372 036 854 775 808 a 9 223 372 036 854 775 807 |
| `float`   | 32 bits; aproximadamente 6–7 dígitos significativos             |
| `double`  | 64 bits; aproximadamente 15–16 dígitos significativos           |
| `char`    | 16 bits; una unidad UTF-16, de 0 a 65 535                       |
| `boolean` | `true` o `false`                                                |

```java
int edad = 20;
long total = 4_320_000_000L;
float nota = 6.5f;
double precio = 19.99;
char letra = 'A';
boolean aprobado = true;
String nombre = "Ana";
```

`char` usa comillas simples; un carácter visible puede necesitar más de una unidad UTF-16. `'AB'` y `''` son inválidos.

## Referencias
[[Strings|String]], [[Arreglos (Arrays)|arrays]] y tipos de [[Clases y objetos|clase]] son tipos de referencia. Una referencia permite localizar un objeto; la «flecha» es una analogía, no una dirección numérica que puedas manipular en Java. `null` indica ausencia de objeto.

Enums y records ya figuraban como ejemplos de tipos; su estudio queda pendiente.

## Errores comunes
- `int saldo = 1.000;` no compila: el literal es `double`. Para mil usa `1_000`.
- Los enteros pueden desbordarse sin avisar; consulta [[Operadores aritméticos básicos]].
- [[Type Casting]] no significa que cualquier tipo pueda convertirse en cualquier otro.
- Las [[Variables y scopes|variables locales]] necesitan asignación antes de leerse.

Fuente: [JLS §4.2 y §4.3](https://docs.oracle.com/javase/specs/jls/se25/html/jls-4.html).

## Material de clase conservado

![[Pasted image 20260905172213.png]]

> [!warning] Por verificar
> Falta la grabación enlazada originalmente: `Recording 20260923154132.m4a`. Localiza el archivo y vuelve a insertarlo; no se ha supuesto su contenido.

> [!warning] Por verificar
> Falta la grabación enlazada originalmente: `Recording 20260923161006.m4a`. Localiza el archivo y vuelve a insertarlo; no se ha supuesto su contenido.

> [!note] Matiz de la imagen original
> La tabla ilustrada simplifica «vida útil». Para distinguir scope y recuperación de memoria, consulta [[Variables y scopes]].

