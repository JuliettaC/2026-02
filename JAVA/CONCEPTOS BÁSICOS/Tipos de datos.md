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
> [!summary] Qué es
> El tipo define los valores y operaciones permitidos: primitivos o referencias.

## Primitivos

| Tipo | Tamaño y rango / precisión |
|---|---|
| byte | 8 bits; −128 a 127 |
| short | 16 bits; −32 768 a 32 767 |
| int | 32 bits; −2 147 483 648 a 2 147 483 647 |
| long | 64 bits; −2⁶³ a 2⁶³−1 |
| float | 32 bits; ~6–7 dígitos significativos |
| double | 64 bits; ~15–16 dígitos significativos |
| char | 16 bits; unidad UTF-16, de 0 a 65 535 |
| boolean | true o false |

```java
int edad = 20;
long total = 4_320_000_000L;
float nota = 6.5f;
double precio = 19.99;
char letra = 'A';
boolean aprobado = true;
String nombre = "Ana";
```

**Importante:** char usa comillas simples; un carácter visible puede ocupar más de una unidad UTF-16. 'AB' y un literal char vacío son inválidos.

## Referencias

- Guardan una referencia al objeto, no una dirección numérica manipulable.
- String, arrays y tipos de clase son referencias; **null** indica ausencia.
- Records y enums también declaran tipos; las colecciones usan envolventes como **Integer**.

## Elegir un tipo y sobredimensionamiento

- Elige según **rango, operaciones y precisión**.
- Un receptor más amplio no cambia el tipo del cálculo.
- Reducir todo a byte/short no garantiza ahorrar: hay promociones a int y costes dependientes de la JVM.
- float/double son aproximaciones binarias; para dinero exacto define representación decimal y redondeo.

## Errores comunes

- **1.000** es un double, no mil. Para mil usa **1_000**.
- Los enteros pueden desbordarse sin excepción.
- Casting no permite convertir cualquier tipo a cualquier otro.
- Las locales requieren asignación antes de leerse.

## Material de clase conservado

> [!warning] Por verificar
> Faltan Recording 20260923154132.m4a y Recording 20260923161006.m4a. Su contenido no se ha supuesto.

> [!note] Importante
> La imagen simplifica «vida útil»: distingue alcance del nombre y recuperación de memoria.

![[Pasted image 20260905172213.png]]

## Relacionado

[[Strings|String]] · [[Arreglos (Arrays)|arrays]] · [[Clases y objetos|clase]] · [[Records y enums]] · [[Colecciones y genéricos]] · [[Operadores aritméticos básicos]] · [[Type Casting]] · [[Variables y scopes|variables locales]] · [[Variables y scopes]]

Fuente: [JLS §4.2 y §4.3](https://docs.oracle.com/javase/specs/jls/se25/html/jls-4.html).
