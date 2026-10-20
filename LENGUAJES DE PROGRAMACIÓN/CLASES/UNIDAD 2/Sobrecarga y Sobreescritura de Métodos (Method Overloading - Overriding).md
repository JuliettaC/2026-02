Para no confundirlos nunca al leer código:

- **Sobrecarga (Overloading) = Mismo nombre, distintos ingredientes (parámetros).** Ocurre normalmente en la misma clase (ej. `sumar(int a, int b)` y `sumar(double a, double b)`).
- **Sobreescritura (Overriding) = Hijo reemplaza la receta del padre.** El hijo hereda un método del padre y lo vuelve a escribir con **exactamente el mismo nombre y los mismos parámetros** para cambiar lo que hace.

**Las 4 trampas clásicas al leer código:**
1. **Falsa sobrecarga cambiando solo el tipo de retorno (Error Semántico):** Si dos métodos tienen el mismo nombre y los mismos tipos de parámetros (ej. `int calcular(int a)` y `double calcular(int a)`), Java no sabe cuál llamar y no compila. Cambiar el retorno no basta; **deben cambiar los parámetros**.
2. **Bajar la visibilidad al sobreescribir (Error Semántico):** Si el método en el padre es `public`, en el hijo no puede ser `private` ni dejarse vacío (default). El hijo no puede ser más restrictivo que el padre.
3. **Intentar sobreescribir un método `final` o `static` (Error Semántico):** Si el método del padre tiene la palabra `final`, está bloqueado y el hijo tiene prohibido sobreescribirlo.
4. **Error de tipeo en el nombre al sobreescribir (Error Lógico o Semántico):** Si el padre tiene `calcularImpuesto()` y el hijo escribe `calcularInpuesto()` (con 'n'), Java cree que es un método nuevo y no reemplaza al del padre (Error Lógico). Si el hijo le puso la etiqueta `@Override` arriba, el compilador te avisa del error de tipeo y no compila (Error Semántico).