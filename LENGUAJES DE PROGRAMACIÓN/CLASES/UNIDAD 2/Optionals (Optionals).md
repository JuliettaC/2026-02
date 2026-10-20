Un `Optional` es como una **caja sellada** que puede contener un objeto o estar completamente vacía. En lugar de devolver `null` (lo cual es peligroso porque al menor descuido explota con un `NullPointerException`), los métodos modernos devuelven un `Optional`. Esto obliga a quien recibe la caja a abrirla con métodos seguros que previenen errores en ejecución.

Un **Optional** es literalmente como un **paquete de regalo** 🎁:
- Puede tener algo adentro.
- O puede venir completamente **vacío**.
El gran problema al leer código ocurre cuando el programador intenta abrir o usar ese paquete de manera incorrecta.

**Las 4 trampas clásicas al leer código con Optionals:**
1. **Llamar a `.get()` sin verificar antes (Error de Ejecución):** Si abres la caja con `.get()` cuando está vacía (`Optional.empty()`), compila sin problemas, pero explota en ejecución lanzando un `NoSuchElementException`. Antes de usar `.get()`, debe verificarse con `.isPresent()`, o mejor aún, usar `.orElse("valorPorDefecto")`.
ABRIR A LA FUERZA usar .get() directamente sin preguntar que hay dentro. Si esta vacia el programa explota con un no NoSuchElementException (error de ejecución)

2. **Pasar `null` a `Optional.of()` (Error de Ejecución):** `Optional.of(valor)` exige que el valor no sea nulo. Si le pasas un `null`, explota inmediatamente con `NullPointerException`. Si el valor puede ser nulo, debe usarse `Optional.ofNullable(valor)`.
METER UN NULO A AL FUERZA Usar `Optional.of(variable)` cuando esa variable vale `null`.
-> `Optional.of()` odia el `null`. Si le pasas un `null`, explota de inmediato con `NullPointerException`. _(Para admitir nulos se debe usar `Optional.ofNullable(...)`)_.

3. **Usar `Optional` en atributos de clases o parámetros (Error Lógico / Diseño):** Los `Optionals` fueron creados exclusivamente como **tipos de retorno** para métodos. Declarar atributos o parámetros como `Optional` ensucia el código y rompe su propósito.
4. **Comparar Optionals con `== null` (Error Lógico):** Quien devuelve un `Optional` nunca debería devolver `null`, sino `Optional.empty()`. Hacer `if (miOptional != null)` no verifica si hay un dato adentro; para eso se usa `if (miOptional.isPresent())`
