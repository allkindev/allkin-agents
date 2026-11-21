# Administrator

El administrador de la máquina donde funciona Allkin, y del propio Allkin. Root mediante `sudo`,
instala y desinstala software, actualiza el sistema, gestiona servicios, usuarios, discos,
reglas de cortafuegos y SSH, escribe scripts de automatización y crea las acciones de Allkin —
sea cual sea el sistema: Debian, Ubuntu, Fedora, RHEL, Arch, openSUSE, Alpine, Void, Gentoo, con
systemd o sin él, en un contenedor o bajo WSL.

## Lo que hace

- **Software**: lo instala, actualiza y desinstala desde fuentes de confianza (la distribución
  primero), dice de dónde viene y cómo se mantendrá al día.
- **Actualizaciones del sistema**: muestra lo que va a cambiar, la seguridad primero, aplica, y
  le dice si hace falta reiniciar y por qué.
- **Servicios, usuarios, discos, red**: arranca, detiene, activa, limpia — guardando una copia de
  cada archivo que cambia y comprobando una configuración antes de recargarla.
- **Cortafuegos y SSH**: abre, cierra, restringe — en el cortafuegos que la máquina ya usa, sin
  cortar nunca su acceso, con la vuelta atrás preparada antes de cualquier cambio arriesgado.
- **Scripts de automatización**: repetibles sin daño, con un ensayo en seco, un registro y una
  notificación si fallan; usted los lanza como atajo, o una acción de Allkin los ejecuta.
- **Allkin**: lo conoce a fondo — su servicio, registros, actualizaciones, copias de seguridad,
  registro de eventos, páginas y ajustes. Crea él mismo las acciones y los agentes; para lo que le
  corresponde a usted (los derechos, los ajustes, instalar una integración), le da la ruta exacta
  en la interfaz.
- **Una ficha de la máquina y un registro de cada cambio**, en su carpeta: lo instalado, cómo
  accede usted, lo que se cambió, cuándo y cómo deshacerlo.

Nunca apaga la máquina, nunca concede un derecho (ni a sí mismo ni a otro agente), nunca edita a
mano la configuración de Allkin, nunca toca el registro de eventos, nunca deshace las
protecciones de Allkin sobre el cortafuegos y SSH, nunca descarga y ejecuta un script de una vez.

## Lo que necesita

Un agente importado llega sin más derechos que los predeterminados. En su página de Agente:

| Ajuste | Por qué |
|---|---|
| **Acceso al sistema: Administrador del sistema** | Su oficio: cualquier comando, root mediante `sudo`. Cada comando se le muestra primero en una tarjeta. |
| **Puede programar acciones** + competencia **Gestionar acciones** | Para crear las acciones de Allkin. Usted aprueba cada creación y cada eliminación. |
| **Puede crear, reescribir y eliminar otros agentes** | Para crear agentes para usted (nacidos sin ningún derecho) y mantener sus roles al día. |
| **Puede buscar y leer páginas en la web** | Para leer la documentación de un programa, unas notas de versión, un aviso de seguridad. |
| **Puede lanzar subtareas** | Para revisar registros o configuraciones largos sin llenar su conversación. |
| **Memoria** (activada por defecto) | Para recordar cómo accede usted a la máquina y las decisiones que tomó. |
| **Competencias: Administración de sistemas, Administración de Allkin, Informe de incidente** | Sus métodos; se descargan cuando se las da. |

### Root, y las tarjetas

Allkin funciona con el usuario `allkin`, que puede usar `sudo` sin contraseña: Administrator es
root. **Aun así, cada comando pasa por su tarjeta** — Aprobar, **Aprobar para esta sesión**
(todos los comandos de esta conversación, práctico para un trabajo largo), **Permitir siempre…**
(un patrón guardado en su página) o Rechazar. Esa tarjeta es el muro de Allkin, no una elección
del agente: ningún agente puede quitarla.

### Automatizaciones sin usted

Una acción que despierta a Administrator sin nadie delante solo puede ejecutar comandos si usted
activa la **aprobación automática** de esa acción (en la página de la acción) y su página aprueba
esos comandos automáticamente. Un script que debe ejecutarse con regularidad es más sencillo:
Administrator lo escribe y le da el comando; usted crea la acción que lo ejecuta (Acciones ›
Nueva acción) o lo añade como atajo.

## Cómo usarlo

1. Dele los derechos de arriba, y las competencias.
2. Pida: «Conozca esta máquina». Reconoce el sistema, escribe la ficha de la máquina y le
   pregunta una vez lo que no puede observar — cómo accede usted, qué debe seguir funcionando.
3. Después pida lo que quiera: «Instale nginx y abra el puerto 443», «Actualice el sistema»,
   «Cierre todo salvo SSH desde mi red», «Cada domingo por la noche, limpie los registros»,
   «¿Por qué Allkin va lento?».
4. Apruebe en las tarjetas — una vez, o para la sesión.
