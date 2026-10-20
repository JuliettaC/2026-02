**Loops y Condicionales:** Poner un punto y coma justo después de la condición (`if (x == 0);` o `for(...);`), lo que desvincula el bloque de código siguiente (error lógico).
 **Tamaño y Acceso:** En `Array` se usa la propiedad `.length` y corchetes `arr[0]`. En `ArrayList` se usa el método `.size()` y `.get(0)`. Cruzarlos es un error de compilación.
 **Tipos:** `ArrayList` no acepta tipos primitivos directamente (`ArrayList<int>` no compila, debe ser `ArrayList<Integer>`).
### Manejo de Excepciones (Exception Handling)
Piensa en esto como una **red de seguridad para trapecistas**:
- **`try` (Intentar):** Aquí metes el código peligroso que podría explotar en ejecución (ej. dividir o leer un archivo).
- **`catch` (Atrapar):** Es la red. Si algo explota dentro del `try`, el programa salta inmediatamente al `catch` para manejar el fallo sin que la aplicación muera.
- **`finally` (Finalmente):** Es el equipo de limpieza. Este bloque se ejecuta **siempre**, haya explotado algo o no (incluso si hay un `return` antes).
**Las 4 trampas clásicas al leer código con Excepciones:**
1. **Orden de los `catch` invertido (Error Semántico):** Si pones varios `catch`, debes atrapar primero el error más específico (el hijo, ej. `ArithmeticException`) y al final el más general (el padre, ej. `Exception`). Si pones `Exception` primero, este atrapa absolutamente todo y el `catch` de abajo queda como código inalcanzable; no compila.
2. **`try` huérfano (Error Sintáctico/Semántico):** Un bloque `try` no puede ir solo. Está obligado a tener al menos un `catch` o un `finally` (o ambos).
3. **`return` engañoso frente a `finally` (Error Lógico):** Si ves un `return` dentro del `try`, podrías pensar que el método termina ahí mismo y se salta el resto. En realidad, el bloque `finally` se ejecuta **siempre** antes de que el método termine de salir. Si el `finally` también tiene un `return`, sobrescribe al del `try`.
4. **Excepción verificada no manejada (Error Semántico):** Si un método avisa en su firma que lanza un error verificado usando `throws Exception`, quien llame a ese método está **obligado** a meter esa llamada dentro de un `try-catch` (o declarar `throws` también). Si lo llama directo sin red de seguridad, no compila.

## Tipos de errores
### Léxico
**Palabra mal escrita.** El compilador no reconoce el término o símbolo,
*ej. Faltas de ortografía en palabras clave (`publci`, `Sring`), variables que empiezan con números (`int 1num`), o comillas sin cerrar.*
### Sintáctico 
**Falla de gramática puntuación.** Las palabras existen, pero el orden o los símbolos están mal.
*ej. Olvidar un `;`, dejar llaves `{}` o paréntesis `()` sin cerrar, o usar corchetes donde van paréntesis.*
### Semántico 
**Sin sentido para la reglas de tipos y alcance.** La gramática es correcta, pero las piezas no encajan.
*ej. Asignar un texto a un número (`int x = "hola";`), usar una variable no estática dentro de `static`, o llamar a un método que esa clase no tiene (como `.length` en `ArrayList`)*
### Ejecución
**Operación imposible en vivo.** Compila bien, pero explota al correr con los datos.
*ej. Dividir por cero, pedir un índice fuera de rango (`IndexOutOfBounds`), o usar un objeto `null` (`NullPointerException`).*
### Lógico 
**El código miente.** No explota ni da error, pero calcula mal.
*ej. Usar `==` para comparar `String`, perder decimales al dividir enteros, o poner mal el signo de una condición (`<` en vez de `>`).*

