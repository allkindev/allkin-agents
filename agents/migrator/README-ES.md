# Migrador

Un agente que trae a Allkin sus agentes de **OpenClaw** (antes Clawdbot, Moltbot) o de
**NanoClaw**. Dele un zip de su antigua instalación: deja fuera los secretos, reescribe para
Allkin el rol y la memoria de cada agente, convierte sus competencias y le entrega un archivo por
agente para importar, con una breve lista de lo que queda por hacer.

El objetivo es una buena migración, no una copia perfecta: lo que encaja simplemente en Allkin se
traslada, el resto se le enumera.

## Lo que hace

- Reconoce una instalación de OpenClaw o NanoClaw (las dos organizaciones de NanoClaw) y enumera lo
  que contiene: agentes, roles, memorias, notas, competencias, tareas programadas, canales.
- Le pregunta, con un solo formulario, qué migrar.
- Escribe un rol por agente a partir de su identidad, su alma y sus reglas; conserva sus hechos
  duraderos como memoria y sus notas como archivos.
- Convierte las competencias en un repositorio que usted añade en la Configuración; los scripts
  que no pueden ejecutarse en Allkin se apartan, con el motivo.
- Enumera las acciones que crear, los servicios y canales que conectar, los derechos que conceder.

## Lo que necesita

| Ajuste | Por qué |
|---|---|
| **Competencia: Migrar agentes** | Todo su método y sus scripts; se descarga al crear el agente. |
| **Memoria** (activada por defecto) | Para recordar lo que migró. |

Nada más: trabaja en su propia carpeta. Si le da el derecho «Puede programar acciones» y la
competencia «Gestionar acciones», también puede crear él mismo las acciones, cada una aprobada
por usted.

## Cómo usarlo

1. En la máquina antigua, haga un zip de la instalación:
   - OpenClaw: `cd ~ && zip -r openclaw.zip .openclaw -x '.openclaw/agents/*/sessions/*' '*/node_modules/*'`
   - NanoClaw: `zip -r nanoclaw.zip nanoclaw -x '*/node_modules/*' 'nanoclaw/data/sessions/*'`
2. Abra una conversación con el Migrador, adjunte el zip y pídale la migración.
3. Responda a su formulario y siga su lista: importe cada archivo (el «+» de la lista de agentes ›
   Importar un agente), añada el repositorio de competencias, conceda derechos, conecte servicios.

## Seguridad

Las credenciales, las transcripciones y los valores del `.env` nunca se extraen; cada token o
clave de la configuración se sustituye; un archivo se rechaza mientras quede algo que parezca un
secreto. El código de la antigua plataforma se lee, nunca se ejecuta. Cada agente importado llega
sin ningún derecho y pasa por la tarjeta de identidad y su botón Verificar, como toda
importación. Elimine el zip de la carpeta `Upload/` del agente al terminar.
