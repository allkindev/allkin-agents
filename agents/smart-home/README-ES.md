# Smart Home

El administrador de su Home Assistant. Smart Home hace allí lo que usted haría en su interfaz, más
rápido y con más constancia: incorpora los dispositivos nuevos con usted, nombra todo según el
esquema que usted eligió, escribe sus automatizaciones y construye sus paneles — leyendo primero,
mostrando lo que va a cambiar y guardando una vuelta atrás.

## Lo que hace

- **Dispositivos nuevos**: «escuche los dispositivos nuevos» — abre la red Zigbee (ZHA o
  Zigbee2MQTT), Z-Wave o RFXCOM, oye lo que llega, le dice qué es cada dispositivo y le pregunta
  su nombre, su habitación y qué ocultar. Después cierra la red.
- **Nombres**: propone esquemas de nombres con ejemplos de su propia casa — `light.lustre_salon`,
  `binary_sensor.do_entree` — o toma el suyo, renombra en lote y repara las automatizaciones y los
  paneles que citaban los identificadores antiguos.
- **Habitaciones, plantas, etiquetas**: creadas, ordenadas, cada dispositivo en su sitio.
- **Automatizaciones, scripts, escenas, ayudantes**: usted dice «cuando se abra la puerta de
  entrada por la noche, encienda el pasillo tres minutos»; él lo reformula, comprueba cada
  entidad, valida, crea y prueba con su acuerdo.
- **Paneles**: por uso y por pantalla — un teléfono, una tableta de pared —, como paneles nuevos,
  nunca encima de los suyos sin guardar la versión anterior.
- **El día a día**: «apague el salón», «qué temperatura hay arriba».
- **La salud**: lo que Home Assistant señala, las integraciones con error, las entidades no
  disponibles, las pilas bajas, los dispositivos mudos, las actualizaciones pendientes.

Nunca adivina un identificador, nunca deja una red abierta, no guarda ninguna contraseña, y no
puede detener Home Assistant ni apagar su máquina.

## Lo que necesita

Un agente importado llega sin más derechos que los predeterminados. En su página Agente:

| Ajuste | Por qué |
|---|---|
| **Servicios externos activados: Home Assistant** | Cree el servicio «Home Assistant» (página Servicios) con la dirección de su instalación y un token de acceso de larga duración de un administrador (en Home Assistant: su perfil → Seguridad → Tokens de acceso de larga duración), pruébelo y autorice a Smart Home a usarlo. El token se queda en Allkin. |
| **Servicios externos en solo lectura**: desactivado | Activado, Smart Home solo puede leer y escuchar. |
| **Competencia: Administración de Home Assistant** | Su método; se descarga cuando se la da. |
| **Puede programar acciones** + competencia **Gestionar acciones** | Para un control de salud semanal. Usted aprueba cada acción que crea. |
| **Puede buscar y leer páginas en la web** | Para consultar el manual de un aparato o su gesto de emparejamiento. Opcional. |
| **Memoria** (activada por defecto) | Para recordar sus preferencias. |

## Lo que verá

Leer su instalación no le pide nada. **Cada cambio muestra una tarjeta de validación** en la
conversación — un renombrado, una habitación, un panel guardado, una red abierta —, una sola para
todo el lote, y puede aprobar para la sesión. El interruptor **«Actuar sin validación»** del
servicio quita las tarjetas para todos los agentes, también cuando no hay nadie: déjelo
desactivado, salvo que quiera que una acción modifique su instalación por sí sola.

## Cómo usarlo

1. Cree el servicio Home Assistant y autorícelo en la página de Smart Home.
2. Diga: «Eche un vistazo a mi instalación.» La recorre, le dice lo que ha encontrado y le
   pregunta por dónde empezar.
3. Pida después con sus palabras: «escuche los dispositivos Zigbee nuevos», «renombre bien la
   cocina», «haga un panel para la tableta de la entrada».

## Límites

- Los archivos escritos a mano en YAML (`configuration.yaml`, paquetes, paneles en modo YAML)
  quedan fuera de su alcance: le dice qué cambiar en ellos.
- Una integración que pide una cuenta o una contraseña la añade usted, en Home Assistant.
- No ve el aspecto de un panel ni si una lámpara se ha encendido de verdad: se lo pregunta.
