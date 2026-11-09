# Analyst

Hace hablar a las tablas. Dé a Analyst una exportación —ventas, facturas, hojas de horas,
respuestas de una encuesta, existencias— y una pregunta, aunque sea vaga. Comprueba lo que contiene
de verdad el archivo, calcula cada cifra con scripts y le entrega una breve nota: lo que muestran
los números, lo que no muestran, y la tabla y el gráfico que lo demuestran.

## Por qué sus cifras son fiables

Un modelo de lenguaje que lee doscientas filas y anuncia su total está adivinando. Analyst nunca lo
hace: cada total, media, recuento y porcentaje sale de un script que lee todo el archivo y calcula
con exactitud, al céntimo. El papel del modelo es hacer las preguntas adecuadas a los datos y decir
qué significan las respuestas.

## Qué hace

- **Lee** archivos CSV, TSV y Excel (.xlsx); encuentra el delimitador, la coma decimal, el orden
  de las fechas.
- **Comprueba primero**: celdas vacías, texto entre los números, filas duplicadas, valores
  escritos de varias formas, fechas ambiguas, y se lo dice antes de calcular.
- **Calcula**: totales, medias y medianas, recuentos, cuotas, por categoría, por cliente, por mes,
  trimestre o semana, con filtros; diferencias y tasas de variación.
- **Dibuja** gráficos sobrios —barras, barras horizontales, líneas— en archivos SVG.
- **Escribe la nota**: primero la respuesta, de tres a cinco hallazgos con sus cifras, lo que se
  dejó fuera, lo que no se puede concluir. Si lo pide, los resultados en un archivo Excel.

## Qué necesita

Un agente importado llega sin más derechos que los predeterminados. En su página de Agente:

| Ajuste | Por qué |
|---|---|
| **Competencia: Análisis de datos** | Su método y sus scripts. Se ejecutan en un marco cerrado: solo Node, sin red, leyendo y escribiendo únicamente su propia carpeta. La primera ejecución le muestra una tarjeta; puede aprobar los scripts de esta competencia para la sesión o para siempre. |
| **Memoria** (activada por defecto) | Para recordar cómo están hechas sus exportaciones y sus definiciones, nunca sus cifras. |

No necesita acceso al sistema, ni web, ni ningún servicio.

## Cómo usarlo

1. **Adjunte el archivo** a su mensaje (debe estar en la carpeta de Analyst para que los scripts lo
   lean) y haga su pregunta: «Aquí están las facturas de 2026: ¿cuáles son nuestros diez mejores
   clientes y qué parte de la facturación representan?»
2. Le dice qué es el archivo y qué es dudoso, y le pregunta una vez lo que no puede saber.
3. Recibe la nota, con las rutas de las tablas de resultados y de los gráficos.

## Límites

Una tabla cada vez: no cruza dos archivos grandes ni construye modelos estadísticos. Los archivos
`.xls` y OpenDocument deben guardarse antes como `.xlsx` o `.csv`. Una fórmula de un libro da el
resultado que el archivo conservó la última vez que se guardó.
