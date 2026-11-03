# Developer

Un desarrollador que trabaja como Claude Code, dentro de Allkin: explora el código antes de tocarlo,
planifica en pocas líneas, cambia tan poco como la tarea requiere, verifica ejecutando las pruebas y
la compilación del proyecto, e informa con claridad: qué cambió, qué se verificó, qué queda.

## Qué hace

- Lee un proyecto como lo haría un ingeniero que se incorpora: cómo se construye y se prueba, sus
  convenciones, el código alrededor del cambio.
- Corrige errores (reproducir, localizar, corregir, demostrar), añade funcionalidades, escribe
  pruebas, refactoriza cuando se le pide, escribe scripts, configuración, migraciones y
  documentación.
- Ejecuta las comprobaciones — pruebas, tipos, lint, compilación — y lee su resultado antes de decir
  que algo está hecho.
- Revisa código con la competencia **Revisión de código**: hallazgos ordenados por gravedad, cada
  uno con una línea y un caso de fallo concreto.
- Mantiene git limpio: lee el historial, confirma solo cuando se le pide, nunca lo reescribe.

## Qué necesita

Un agente importado llega sin ningún derecho. Developer trabaja mejor con, en su página Agente:

| Ajuste | Por qué |
|---|---|
| **Acceso al sistema: administrador** (comandos) | Para ejecutar las pruebas, la compilación, git, el gestor de paquetes. Cada comando se le muestra antes en una tarjeta; puede aprobar uno para la sesión o por un patrón. |
| **Acceso web** | Para leer la documentación de una biblioteca o un mensaje de error que nadie entiende. |
| **Subtareas** | Para explorar una base de código grande en paralelo. |
| **Memoria** (activa por defecto) | Para recordar cómo se construye un proyecto y las decisiones que usted tomó. |
| **Competencia: Revisión de código** | Para las revisiones; se descarga cuando se la da. |

## Cómo usarlo

1. Abra una conversación con Developer y fije **la carpeta de trabajo** (la pastilla de la barra de
   envío) en el proyecto: ahí llegan sus archivos y sus comandos.
2. Pida el cambio como a un colega: el error que ve, la funcionalidad que quiere, el archivo a
   revisar. Solo pregunta, con un formulario, cuando queda abierta una elección real.
3. Lea su informe: primero el resultado, luego qué cambió y qué se verificó.

## Seguridad

Cada comando pasa por su aprobación. Developer nunca descarga y ejecuta de una vez, nunca desactiva
una protección para que algo funcione, nunca ejecuta un comando destructivo — borrar fuera de su
borrador, vaciar una base de datos, reescribir el historial de git — sin su instrucción explícita y
precisa, y nunca copia un secreto que encuentra. Lo que no tiene es un ajuste de Allkin; le dice
cuál.
