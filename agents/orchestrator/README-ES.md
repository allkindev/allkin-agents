# Orchestrator

Su punto de entrada único cuando no quiere pensar a qué agente dirigirse, o cuando un trabajo
necesita a varios. Orchestrator entiende la petición, la divide si hace falta, confía cada parte al
agente mejor situado, comprueba lo que vuelve y le da una sola respuesta.

## Qué hace

- Elige el agente adecuado para una petición y se la confía con un encargo que se basta a sí
  mismo: el objetivo, la tarea, el material, el resultado esperado.
- Coordina varios agentes en un mismo trabajo, en el orden correcto, pasando el resultado de uno
  al siguiente.
- Lee cada respuesta como un revisor: un trabajo incompleto, contradictorio o sin verificar vuelve
  una vez, y después se le comunica tal como está.
- Le da una sola respuesta —el resultado primero, luego quién hizo qué y lo que queda—, nunca las
  respuestas pegadas una tras otra.
- Le dice cuándo ningún agente sirve, y qué modelo de agente serviría.
- Recuerda quién hace bien qué y las preferencias que le ha dado.

## Qué necesita

Un agente importado llega sin más derechos que los predeterminados. En su página de Agente:

| Ajuste | Por qué |
|---|---|
| **Puede comunicarse con los demás agentes** (activado por defecto) | Es todo su oficio. Puede limitarlo a una lista de agentes. |
| **Memoria** (activada por defecto) | Para aprender quién hace bien qué, y sus preferencias. |

No necesita nada más: ni acceso al sistema ni web. Cuantos más agentes especializados tenga
—Writer, Researcher, Analyst, Developer…—, más útil resulta.

## Cómo usarlo

1. Diríjase a Orchestrator como a un asistente que conoce a todo el equipo.
2. Para un trabajo mayor, le da su plan en unas líneas antes de empezar.
3. Recibe una sola respuesta, con las rutas de los archivos producidos.

## Conviene saber

Un agente llamado por Orchestrator trabaja sin nadie delante: lo que requeriría su aprobación (un
comando de la máquina, una publicación) puede ser rechazado. Orchestrator le dice entonces a qué
agente dirigirse directamente, con la petición lista para pegar. Nunca concede un derecho, ni a sí
mismo ni a otro agente.
