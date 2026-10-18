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
> [!summary] Qué es
> String representa texto inmutable; sus métodos consultan o devuelven resultados.

## Métodos frecuentes

| Método | Resultado |
|---|---|
| length() | Cantidad de unidades UTF-16 |
| charAt(i) | Unidad char en i |
| substring(inicio, fin) | Inicio incluido; fin excluido |
| toUpperCase() / toLowerCase() | Texto en mayúsculas / minúsculas |
| equals / equalsIgnoreCase | Contenido / contenido ignorando mayúsculas |
| isEmpty() / isBlank() | Longitud cero / vacío o solo espacios en blanco |

```java
String texto = "Java";
System.out.println(texto.length());       // 4
System.out.println(texto.charAt(0));      // J
System.out.println(texto.substring(1, 3));// av
texto = texto.toUpperCase();
System.out.println(texto);                // JAVA
```

**Importante:** reasignar texto no modifica el objeto original. No todo método devuelve String ni crea un objeto nuevo.

## Comparar texto

```java
String ingresada = "clave123";
String correcta = new String("clave123");
System.out.println(ingresada == correcta);     // false: referencias diferentes
System.out.println(ingresada.equals(correcta));// true: mismo contenido
```

- **== entre referencias:** identidad. **equals en String:** contenido.
- En otras clases, equals depende de su implementación; los primitivos no tienen ese método.
- equalsIgnoreCase no elimina espacios ni ignora tildes.

## Límites y null

| Operación | Límites válidos |
|---|---|
| charAt(i) | 0 ≤ i < length() |
| substring(inicio, fin) | 0 ≤ inicio ≤ fin ≤ length() |

- Un índice incorrecto causa una excepción.
- Invocar métodos sobre null causa **NullPointerException**.

**Referencia posiblemente null:** compruébala antes de llamar métodos; el ejemplo está en [[Operadores lógicos#&& frente a &]].

**Importante:** && evita la segunda evaluación si la referencia es null. Array usa **length**; String, **length()**.

## Mención conservada: Integer Cache

- Integer envuelve un int; compara valores con **equals**.
- El boxing de constantes entre **−128 y 127** garantiza identidad compartida.
- Integer.valueOf garantiza caché en ese intervalo y puede ampliarlo.
- Fuera del intervalo no supongas identidades iguales ni siempre distintas.

## Relacionado

[[Variables y scopes|variable]] · [[Exception Handling|excepciones]] · [[Operadores lógicos|&&]] · [[Arreglos (Arrays)|array.length]]

Fuentes: [API String](https://docs.oracle.com/en/java/javase/25/docs/api/java.base/java/lang/String.html), [JLS §5.1.7](https://docs.oracle.com/javase/specs/jls/se25/html/jls-5.html#jls-5.1.7) y [Integer.valueOf](https://docs.oracle.com/en/java/javase/25/docs/api/java.base/java/lang/Integer.html#valueOf(int)).
