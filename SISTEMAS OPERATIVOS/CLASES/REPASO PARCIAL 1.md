# 📚 Checklist de Estudio: Primer Parcial de Sistemas Operativos

## Módulo 1: Introducción a los Sistemas Operativos
- [ ] **1.1 Conceptos Fundamentales**
  - [x] [[Definición del Sistema Operativo]]: comprender el rol de intermediario entre hardware y programas que oculta la complejidad física[cite: 1, 3, 6].
  - [x] [[Propósito del SO]]: saber cómo simplifica el uso de la máquina frente al acceso directo al hardware[cite: 1, 3, 6].
  - [x] [[Software Privativo vs Código Abierto]]: dominar las diferencias respecto al acceso al código fuente, licencias, estudio y modificación[cite: 6].
  - [ ] [[Ubicación de Shell y GUI]]: entender por qué la interfaz de usuario no forma parte estricta del núcleo[cite: 6].
- [ ] **1.2 Funciones y Objetivos Principales**
  - [ ] [[Proveer Abstracciones]]: transformar disco físico en archivos, impresoras en colas y periféricos en controladores[cite: 1, 4, 6].
  - [ ] [[Administrador de Recursos]]: arbitraje y asignación de CPU, memoria RAM, almacenamiento, dispositivos de E/S y red[cite: 1, 6].
  - [ ] [[Capas al abrir un archivo]]: memorizar el flujo de `open()` (Aplicación $\rightarrow$ Biblioteca $\rightarrow$ Kernel $\rightarrow$ File System $\rightarrow$ Driver)[cite: 6].
- [ ] **1.3 Modos de Ejecución y Niveles de Privilegio**
  - [ ] [[Modo Kernel]]: características del máximo nivel de privilegios y control total del hardware[cite: 1, 4].
  - [ ] [[Modo Usuario]]: restricciones de ejecución, aislamiento de fallos y ausencia de acceso directo a E/S[cite: 1, 4].
  - [ ] [[Instrucción Trap]]: entender el mecanismo de trampa/salto para elevar privilegios al kernel de manera segura[cite: 1, 4].
  - [ ] [[Llamada a Procedimiento vs Syscall]]: distinguir llamadas de biblioteca resueltas en espacio de usuario frente a las que cruzan al kernel[cite: 1, 4].

---

## Módulo 2: Arquitectura del Computador y Evolución Histórica
- [ ] **2.1 Componentes de la Arquitectura Básica**
  - [ ] [[Modelo Conceptual]]: interacción entre CPU, Memoria principal y Controladores de E/S[cite: 3].
  - [ ] [[Ciclo de Instrucción]]: pasos de obtención (*fetch*), decodificación y ejecución de instrucciones.
  - [ ] [[Registros de la CPU]]:
    - [ ] [[Registros Generales]]: almacenamiento de resultados intermedios y temporales[cite: 3].
    - [ ] [[Contador de Programa (PC)]]: dirección de la siguiente instrucción a obtener en memoria[cite: 2, 3].
    - [ ] [[Puntero de Pila (SP)]]: localización del tope de la pila (parámetros y variables locales)[cite: 2, 3].
    - [ ] [[Palabra de Estado del Programa (PSW)]]: estado de ejecución del procesador para permitir cambios de contexto[cite: 2].
- [ ] **2.2 Evolución Histórica por Generaciones**
  - [ ] [[Antecedentes Mecánicos]]: Charles Babbage (Máquina Analítica 100% mecánica) y Ada Lovelace (primera programadora)[cite: 2, 3].
  - [ ] [[Generación 1]]: tubos al vacío, tableros de conexiones manuales y posterior llegada de tarjetas perforadas[cite: 2, 3].
  - [ ] [[Generación 2]]:
    - [ ] Incorporación del transistor y computadoras *mainframe* en salas refrigeradas[cite: 2, 3].
    - [ ] Separación clara de roles (diseñadores, constructores, programadores, operadores, mantenimiento)[cite: 2, 3].
    - [ ] Uso para cálculo científico/ingeniería con FORTRAN y ensamblador[cite: 2, 3].
    - [ ] [[Procesamiento por Lotes (Batch)]]: ciclo de tarjetas $\rightarrow$ cinta de entrada $\rightarrow$ programa de control $\rightarrow$ cinta de salida $\rightarrow$ impresión offline (IBM 1401 e IBM 7094)[cite: 2, 3].
    - [ ] Estructura de tarjetas de control: `$JOB`, `$FORTRAN`, `$LOAD`, `$RUN`, `$END`[cite: 2, 3].
  - [ ] [[Generación 3]]:
    - [ ] Circuitos integrados y unificación comercial/científica[cite: 3].
    - [ ] [[Multiprogramación]]: concepto de intercalar CPU mientras otro trabajo espera operaciones de E/S[cite: 2, 3].
    - [ ] Requisito de hardware de protección para aislar programas[cite: 2].
    - [ ] Estándar POSIX (9945-1) y compatibilidad UNIX, System V, BSD, Linux y MINIX 3[cite: 1, 4].
  - [ ] [[Generación 4 y 5]]: microprocesadores, computadoras personales, interfaces gráficas y computación móvil (Android, iOS)[cite: 5, 6].

---

## Módulo 3: Tipos de Sistemas Operativos y Conceptos Clave
- [ ] **3.1 Clasificación por Ámbito**
  - [ ] [[Sistemas Mainframe]]: optimizados para grandes volúmenes de E/S, batch, transacciones críticas y tiempo compartido[cite: 5].
  - [ ] [[Sistemas Embebidos]]: integrados en dispositivos dedicados con recursos limitados (lavadoras, microondas)[cite: 5].
  - [ ] [[Internet de las Cosas (IoT)]]: objetos físicos conectados en red con sensores y actuadores[cite: 5].
  - [ ] [[Sistemas Operativos Móviles]]: optimización de batería y sensores (Android, iOS)[cite: 5, 6].
- [ ] **3.2 Espacio de Memoria de un Proceso**
  - [ ] [[Definición de Proceso]]: programa en ejecución gestionado por el SO[cite: 1, 6].
  - [ ] [[Segmentos de Memoria]]:
    - [ ] Segmento de texto: código binario ejecutable[cite: 1, 4].
    - [ ] Segmento de datos: almacenamiento de variables (crece hacia direcciones superiores)[cite: 1, 4].
    - [ ] Segmento de pila (*stack*): variables locales y retornos de funciones (crece hacia direcciones inferiores)[cite: 1, 4].
    - [ ] Espacio libre: gestión de expansión de memoria dinámica (`brk` tradicional vs. `malloc` moderno)[cite: 1, 4].
- [ ] **3.3 Sistema de Archivos, Protección y E/S**
  - [ ] [[Estructura en Árbol]]: organización jerárquica de directorios (raíz, rutas absolutas y relativas; `/` en UNIX vs. `\` en Windows)[cite: 5].
  - [ ] [[Árbol de Procesos vs Árbol de Archivos]]: corta duración del proceso frente a persistencia de archivos[cite: 5].
  - [ ] [[Dispositivos como Archivos]]: tratamiento en UNIX de periféricos (teclado, pantalla, discos) como archivos especiales[cite: 5].
  - [ ] [[Canales (Pipes)]]: conexión directa entre dos procesos para intercambio de datos[cite: 5].
  - [ ] [[Redirección en el Shell]]: operadores `>`, `<` y tubería `|`[cite: 5].

---

## Módulo 4: Mecánica de Syscalls y Catálogo de Funciones
- [ ] **4.1 El Ciclo de una Syscall (Ejemplo `read`)**
  - [ ] [[Preparación de Parámetros]]:
    - [ ] Registro `RDI`: descriptor de archivo `fd`[cite: 1, 4].
    - [ ] Registro `RSI`: dirección de memoria `&bufer`[cite: 1, 4].
    - [ ] Registro `RDX`: número de bytes `nbytes`[cite: 1, 4].
    - [ ] Convención *System V AMD64 ABI*: 6 primeros argumentos en registros (`RDI`, `RSI`, `RDX`, `RCX`, `R8`, `R9`) y resto en la pila[cite: 1, 4].
  - [ ] [[Traspaso y Ejecución]]:
    - [ ] Asignación del número de servicio en el registro `RAX`[cite: 1, 4].
    - [ ] Ejecución de la instrucción `trap` / `SYSCALL`[cite: 1, 4].
    - [ ] El despachador consulta la tabla de llamadas usando `RAX` como índice y delega en el manejador[cite: 1, 4].
  - [ ] [[Retorno y Códigos de Error]]:
    - [ ] Éxito: retorna cantidad de bytes leídos en cuenta[cite: 1, 4].
    - [ ] Error: retorna `-1` y define la variable `errno`[cite: 1, 4].
    - [ ] Posibilidad de bloqueo: espera pasiva de datos (ej. teclado) mientras el SO ejecuta otro proceso[cite: 1, 4].
- [ ] **4.2 Administración de Procesos**
  - [ ] `fork()`: única vía en POSIX para crear procesos; devuelve `0` al proceso hijo y el `PID` del hijo al padre[cite: 1, 4].
  - [ ] `execve(nombre, argv, envp)`: reemplaza la imagen del proceso por un nuevo ejecutable con sus argumentos y entorno[cite: 1, 4].
  - [ ] `waitpid(pid, &statloc, opciones)`: suspensión del proceso padre a la espera de la terminación del hijo[cite: 1, 4].
  - [ ] `exit(estado)`: terminación del proceso y retorno de estado (código de salida 0 a 255)[cite: 1, 4].
  - [ ] [[Ejecución de un Comando en la Shell]]: ciclo donde la shell hace `fork()`, el hijo ejecuta `execve()` y el padre hace `waitpid()`[cite: 1, 5].
- [ ] **4.3 Administración de Archivos**
  - [ ] `open()`: apertura con flags (`O_RDONLY`, `O_WRONLY`, `O_RDWR`, `O_CREAT`) y retorno del descriptor `fd`[cite: 1, 4].
  - [ ] `read(fd, bufer, nbytes)` y `write(fd, bufer, nbytes)`: lectura y escritura sobre flujos de bytes[cite: 1, 4].
  - [ ] `close(fd)`: liberación del descriptor de archivo para posterior reutilización[cite: 1, 4].
  - [ ] `lseek(fd, desplazamiento, de_donde)`: cambio de posición del apuntador/cursor (acceso aleatorio) devolviendo la posición absoluta[cite: 1, 4].
  - [ ] `stat(archivo, &info)`: consulta de metadatos (tamaño, tipo, modificación) sin leer el archivo[cite: 1, 4].
- [ ] **4.4 Administración de Directorios, Enlaces y Sistema**
  - [ ] `mkdir()` y `rmdir()`: creación y eliminación de directorios vacíos[cite: 1, 4].
  - [ ] `link(nombre1, nombre2)`: asociación de un nuevo nombre al mismo inodo (compartir archivos sin duplicar datos)[cite: 1, 4].
  - [ ] `unlink(nombre)`: eliminación de una referencia de directorio a un inodo[cite: 1, 4].
  - [ ] `mount(dispositivo, punto_montaje, flags)` y `umount()`: acoplar y desacoplar sistemas de archivos (ej. USB en `/mnt`)[cite: 1, 4, 5].
  - [ ] `chdir(ruta)`: cambio del directorio de trabajo actual para acortar rutas de acceso[cite: 1, 4].
  - [ ] `chmod(archivo, modo)`: ajuste de permisos por máscara octal (`4 = r`, `2 = w`, `1 = x`; ej. `0644` = dueño lee/escribe, resto solo lee)[cite: 1, 4, 5].
  - [ ] `kill(pid, señal)`: envío de señales a procesos para manejo asíncrono o terminación[cite: 1, 4].
  - [ ] `tiempo(&segundos)`: conteo del tiempo transcurrido desde la época UNIX (1 de enero de 1970)[cite: 1, 4].
  - [ ] [[Modelo UNIX vs Windows API]]: llamadas secuenciales al sistema en UNIX frente al modelo dirigido por eventos y manejadores en Win32[cite: 1, 4].

# Conceptos Fundamentales

## Introducción a los Sistemas Operativos

~={blue} **Definición Sistema Operativo** =~

SISTEMA OPERATIVO: es un intermediario entre los programas (navegador, reproductor de musica, etc) y las piezas físicas (el hardware: CPU, memoria RAM, discos) de la máquina

Para cumplir este propósito, el SO 
1) **provee abstracciones (hacia las aplicaciones):** oculta la complejidad física del hardware creando modelos sencillos.
2) **administra recursos (hacia el hardware):** coordina y distribuye el uso de la CPU, memoria RAM y los dispositivos de entrada/salida entre todos los programas que lo solicitan, evitando que un solo proceso monopolice el sistema o que cause conflictos con los demás.

~={blue}**Software Privativo vs Código Abierto**=~

|                         | Software Privativo                                                                                                                | Código Abierto                                                                           |
| ----------------------- | --------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------- |
| Acceso al código fuente | es secreto y pertenece a la empresa creadora                                                                                      | está disponible públicamente para cualquier persona                                      |
| Estudio y modificación  | prohíbe por contrato (licencia) cualquier alteración o ingeniería inversa                                                         | permite analizar cómo funcoina por dentro y modificarlo para adaptarlo a tus necesidades |
| Licencias               | otorgan un permiso limitado de uso bajo las condiciones impuestas por el fabricante (ej. pago de licencias por usuario o máquina) | garantizan libertades de uso, redistribución y mejora                                    |


***Que sea de código abierto no siempre significa que sea gratuito; la clave está en la libertad de acceso y modificación del código fuente, no en su precio***

