Piensa en un `Set` (como `HashSet` o `TreeSet`) como una **bolsa sin orden ni posiciones numeradas** donde está prohibido meter dos cosas iguales. A diferencia de un `ArrayList` (que es una fila ordenada con asientos numerados 0, 1, 2...), en un `Set` los elementos están sueltos.

**Las 4 trampas clásicas al leer código con Set:**

1. **Intentar usar `.get(indice)` (Error Semántico):** Como un `Set` no tiene posiciones numeradas (índices), el método `.get(0)` **no existe** en `Set`. Si ves `miSet.get(0)`, el código no compila.
NO TIENE POSICIONES NUMERADAS POR LO TANTO NO SE PUEDE USAR .GET()
2. **Instanciar `Set` directamente con `new Set<>()` (Error Semántico):** `Set` es una interfaz (un contrato), no una clase concreta. Hacer `new Set<>()` no compila; debe usarse una clase que lo implemente, como `new HashSet<>()` o `new TreeSet<>()`.

3. **Asumir que un duplicado reemplaza o lanza error (Error Lógico):** Si agregas un elemento repetido con `.add("A")`, Java no lanza ningún error: simplemente **lo ignora** y `.add()` devuelve `false`. El tamaño (`.size()`) no aumenta.
4. **Meter `null` en un `TreeSet` (Error de Ejecución):** Mientras que `HashSet` permite guardar un `null`, `TreeSet` ordena los elementos automáticamente comparándolos entre sí. Si intentas hacer `.add(null)` en un `TreeSet`, explota en ejecución con `NullPointerException`.
