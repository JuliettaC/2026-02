---
tags:
  - java
  - java/fundamentos
status: aprendido
aliases:
  - "Loops"
  - "for"
  - "while"
---

# Bucles
> [!summary] Qué es
> Repiten instrucciones mediante una condición o un recorrido.

## for

**Uso:** contador. Inicializa una vez, comprueba antes de cada vuelta y actualiza después del cuerpo.

```java
for (int i = 0; i < 3; i++) {
    System.out.println(i);
}
```

## for-each

**Uso:** recorrer arrays o Iterable, como List, sin índices. Un número devuelto por size() no es recorrible.

```java
int[] notas = {5, 6, 7};
for (int nota : notas) {
    System.out.println(nota);
}
```

## while

**Uso:** repetir mientras la condición sea true; puede ejecutar **cero** veces.

```java
int numero = 0;
while (numero < 3) {
    System.out.println(numero);
    numero++;
}
```

## do...while

**Uso:** comprobar después del cuerpo; se ejecuta **al menos una vez** si se alcanza la sentencia.

```java
int numero = 10;
do {
    System.out.println("El numero es: " + numero);
} while (numero < 5);
```

## Errores comunes

- Actualiza la condición para evitar un bucle infinito.
- Índices: **i < datos.length**, no <=.
- do...while lleva **; final**.
- Inicializa el acumulador donde corresponda al total deseado.

## break, continue y variable de recorrido

| Elemento | Efecto |
|---|---|
| break | Sale del bucle al que se aplica |
| continue | Omite el resto de la vuelta |
| continue en for | Pasa por actualización y condición |
| continue en while | Vuelve a la condición |

**Importante:** reasignar la variable de for-each no reemplaza el elemento. Mutar el objeto referenciado sí puede cambiar el objeto compartido.

## Relacionado

[[Arreglos (Arrays)|arrays]] · [[Colecciones y genéricos]] · [[Variables y scopes]] · [[Operadores lógicos]]

Fuente: [JLS §14.12–14.14](https://docs.oracle.com/javase/specs/jls/se25/html/jls-14.html).
