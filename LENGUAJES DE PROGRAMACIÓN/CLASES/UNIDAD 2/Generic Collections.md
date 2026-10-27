Los genéricos (`<T>`) son etiquetas de seguridad para clases y métodos. Permiten definir qué tipo exacto de objeto puede entrar en una estructura (como `ArrayList<String>` o `Caja<Integer>`), de modo que el compilador detecte errores de tipos antes de ejecutar el programa.

**Las 4 trampas clásicas al leer código con Generics:**

1. **Incompatibilidad de tipos (Error Semántico):** Si declaras `Caja<String>`, el compilador bloquea cualquier intento de meter otro tipo de dato (como un `Integer` o `Double`).
    
2. **Colecciones crudas o _Raw Types_ (Error de Ejecución):** Si olvidas poner los diamantes `<>` al declarar una colección (ej. `ArrayList lista = new ArrayList();`), Java asume que guarda `Object` y te deja meter cualquier cosa mezclada (textos, números). El problema revienta al sacar los datos y hacer cast: lanza `ClassCastException` en ejecución.
    
3. **Instanciar el tipo genérico con `new T()` (Error Semántico):** Dentro de una clase genérica `class Caja<T>`, está prohibido hacer `new T()`. Como Java borra los tipos genéricos al compilar (_Type Erasure_), no sabe qué constructor llamar y no compila.
    
4. **Polimorfismo engañoso en genéricos (Error Semántico):** Aunque `Integer` es hijo de `Number`, una `ArrayList<Integer>` **no** es hija de `ArrayList<Number>`. Hacer `ArrayList<Number> lista = new ArrayList<Integer>();` no compila.