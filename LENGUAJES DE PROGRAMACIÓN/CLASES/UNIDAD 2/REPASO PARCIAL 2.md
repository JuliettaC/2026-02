**Loops y Condicionales:** Poner un punto y coma justo después de la condición (`if (x == 0);` o `for(...);`), lo que desvincula el bloque de código siguiente (error lógico).
 **Tamaño y Acceso:** En `Array` se usa la propiedad `.length` y corchetes `arr[0]`. En `ArrayList` se usa el método `.size()` y `.get(0)`. Cruzarlos es un error de compilación.
 **Tipos:** `ArrayList` no acepta tipos primitivos directamente (`ArrayList<int>` no compila, debe ser `ArrayList<Integer>`).

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

