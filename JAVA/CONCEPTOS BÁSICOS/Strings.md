---
tags:
  - java
  - java/fundamentos
status: aprendido
aliases:
  - "Cadenas y Métodos (Strings and Methods)"
  - "String"
---

# Strings
> [!summary] En una frase
> String representa texto inmutable; sus métodos permiten consultarlo o producir un resultado.

## Métodos frecuentes
| Método | Resultado |
|---|---|
| `length()` | Cantidad de unidades UTF-16 |
| `charAt(i)` | Unidad char de la posición i |
| `substring(inicio, fin)` | Texto entre inicio incluido y fin excluido |
| `toUpperCase()` / `toLowerCase()` | Texto en mayúsculas / minúsculas |
| `equals(otro)` | Comparación de contenido |
| `equalsIgnoreCase(otro)` | Comparación sin distinguir mayúsculas |

```java
String texto = "Java";
System.out.println(texto.length());       // 4
System.out.println(texto.charAt(0));      // J
System.out.println(texto.substring(1, 3));// av
texto = texto.toUpperCase();
System.out.println(texto);                // JAVA
```

El objeto original no cambia: reasignas la [[Variables y scopes|variable]] al resultado. No todos los métodos devuelven String ni necesariamente crean un objeto nuevo.

## Comparar texto
```java
String ingresada = "clave123";
String correcta = new String("clave123");
System.out.println(ingresada == correcta);     // false: referencias diferentes
System.out.println(ingresada.equals(correcta));// true: mismo contenido
```

`==` entre referencias comprueba identidad; los primitivos no tienen métodos `equals`. Para objetos en general, el significado de `equals` depende de la clase.

## Límites y null
- `charAt`: `0 ≤ i < length()`.
- `substring`: `0 ≤ inicio ≤ fin ≤ length()`; fin puede ser igual a length.
- Los índices incorrectos producen [[Exception Handling|excepciones]].
- Llamar métodos sobre `null` produce NullPointerException; comprueba la referencia cuando puede ser null.

```java
String respuesta = null;
if (respuesta != null && respuesta.equalsIgnoreCase("sí")) {
    System.out.println("Confirmado");
}
```

[[Operadores lógicos|&&]] evita evaluar el segundo operando si el primero es falso. Para tamaños, recuerda [[Arreglos (Arrays)|array.length]] frente a String.length().

## Mención conservada: Integer Cache
Integer es un objeto que envuelve un int. El boxing de valores constantes entre −128 y 127 garantiza reutilización de identidad; Integer.valueOf también garantiza caché en ese intervalo y puede ampliarlo. Fuera de él no asumas objetos siempre distintos. Compara valores con equals, no basándote en la caché.

Fuentes: [API String](https://docs.oracle.com/en/java/javase/25/docs/api/java.base/java/lang/String.html), [JLS §5.1.7](https://docs.oracle.com/javase/specs/jls/se25/html/jls-5.html#jls-5.1.7) y [Integer.valueOf](https://docs.oracle.com/en/java/javase/25/docs/api/java.base/java/lang/Integer.html#valueOf(int)).
