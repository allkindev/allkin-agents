# Sentinel

Vigila sus servidores. Sentinel hace su ronda por las máquinas que usted le confía, con comandos
que no modifican nada, compara con la vez anterior y le dice qué requiere su atención antes de que
se convierta en una avería: el disco que se llena, el certificado que caduca en diez días, la copia
de seguridad detenida desde hace tres semanas.

## Qué hace

- **Rondas**: disco, memoria y carga, servicios que deben funcionar, actualizaciones pendientes y
  de seguridad, reinicio necesario, certificados, copias de seguridad, inicios de sesión fallidos
  y puertos abiertos, errores en los registros.
- **Tendencias**: guarda las lecturas de cada ronda y le dice adónde llevan: «`/var` al 91 %,
  lleno en unos diez días».
- **Un informe ordenado por urgencia**: crítico, aviso, nota; «sin novedad» cabe en una línea.
  Cada hallazgo viene con el comando exacto que propone, que solo ejecuta si usted lo pide.
- **Una ficha por máquina**: lo que debe funcionar en ella, lo que allí es normal, sus umbrales.
- **Incidentes**: cuando algo falla, un diagnóstico paso a paso y un informe escrito.
- **Por sí solo** mediante las Acciones de Allkin: una ronda cada mañana o cada semana.

Nunca repara por su cuenta, nunca apaga una máquina, nunca lee un secreto.

## Qué necesita

Un agente importado llega sin más derechos que los predeterminados. En su página de Agente:

| Ajuste | Por qué |
|---|---|
| **Servicios: sus máquinas por SSH** | Cree un servicio «Máquina por SSH» por servidor (página Servicios), pruébelo y autorice a Sentinel a usarlo. Las credenciales se quedan en Allkin. |
| **Acceso al sistema: Solo lectura** | Para comprobar la máquina donde funciona Allkin, en solo lectura, sin aprobación. |
| **Puede programar acciones** + competencia **Gestionar acciones** | Para rondas periódicas. Usted aprueba cada acción que crea. |
| **Competencias: Control de salud de servidores, Informe de incidente** | Sus métodos; se descargan cuando se las da. |
| **Memoria** (activada por defecto) | Para recordar sus máquinas y sus umbrales. |

### Rondas sin usted

Cada comando en una máquina por SSH le muestra una tarjeta; puede aprobar para la sesión o guardar
patrones en la página de Sentinel. Una ronda **iniciada por una acción**, sin nadie delante, solo
se ejecuta en las máquinas cuyo servicio tiene activado el interruptor **«Actuar sin validación»**.
Ese interruptor permite a Sentinel ejecutar comandos allí por su cuenta: actívelo solo para una
**cuenta SSH que solo pueda leer** en esa máquina (un usuario corriente sin sudo, miembro de los
grupos que leen los registros).

## Cómo usarlo

1. Cree los servicios SSH y autorícelos en la página de Sentinel.
2. Pida: «Haga una primera ronda.» Descubre cada máquina, escribe su ficha y le pregunta una vez
   lo que no puede observar: qué debe funcionar, adónde van las copias de seguridad.
3. Acepte la acción que propone para las rondas periódicas, o pida «haga su ronda» cuando quiera.
4. Cuando avise de algo, decida: le da el comando; usted dice sí o lo ejecuta usted mismo.
