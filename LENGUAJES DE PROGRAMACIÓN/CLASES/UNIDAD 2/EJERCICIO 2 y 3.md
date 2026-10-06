```text
6 static final int NOTA_MINIMA = 10;
18 
19 for (int i = 0; i <= notas.length(); i++) {
/* el error esta en 
i <=  y notas.length()*/
22 return suma / cantidad;
/* double con int */

25 public String estado(double nota) {
26 String resultado;
// no tiene ningun valor inicializar variable
27 if (nota >= 4.0) {
28 resultado = 'aprobado';
29 }
30 return resultado;
31 }
/* no esta el caso de los reprobados 
y en la 28 faltan comillas */
34

39 for (int i = 0; i < cantidad; i++ {
// falta parentesis

47 public String resumen() {
48 int total = cantidad
49 int aprobados = contarAprobados();
50 String linea = "Aprobados: " + aprobados + " de " + total;
51 int reprobados = total - aprobados
52 if (reprobados > 0) {
53 String aviso = "Hay reprobados";
54 }
55 System.out.println(aviso);
56 return linea;
57 }

/* En el fragmento de resumen, la variable aviso no está disponible fuera de su bloque
aviso se declaró dentro del if: usarlo fuera del bloque causa error de compilación; no se vuelve null */

59 public void ajustarMinimo(int nuevo) {
60 NOTA_MINIMA = nuevo;

/* se intenta cambiar el valor de NOTA_MINIMA que se declaro como variable final */

65 int porcentaje = notas[i] / 7 * 100;

/* hay algo raro pero nose que es 
calculo decimal a entero se pierde prec */

71 nombre = nombre;

/* nombre = nombre 
No guarda nada en el objeto, el valor se pierde en cuanto termina el método.  
this.nombre = nombre; 
Asigna el dato recibido al atributo del objeto para actualizar el atributo mientras el objeto exista y no se cambie otra vez. */

74 } 
/* corchete que sobra */

76 


```

![[Recording 20260909160951.m4a]]


# ejercicio 3

```text
11 int saldo = 1.000;
/*
1.000 es un literal double equivalente a 1.0; asignarlo directamente a int no compila. Para mil: int saldo = 1_000;
*/
24 switch (tipo) {
/* 
falta el break
*/
42 return tipo == "e";
/*
*/

```


> [!warning] Por verificar
> Se conservan los fragmentos originales con números de línea: contienen errores deliberados y no son ejemplos ejecutables. Falta el código completo para decidir la escala de NOTA_MINIMA, el tipo de notas[i] y la corrección exacta del porcentaje.

### Correcciones de consulta
- Arrays usa length sin paréntesis; para recorrer: i < notas.length.
- Un promedio debe convertir un operando antes de dividir si ambos son enteros.
- String usa comillas dobles; resultado debe asignarse en cada ruta antes del return.
- NOTA_MINIMA es final y no se puede reasignar.
- tipo == "e" compara identidad; para contenido: "e".equals(tipo).


## Consulta de conceptos Java
[[Atributos y métodos#this]] · [[Variables y scopes]] · [[final]] · [[Type Casting]] · [[Strings]]
