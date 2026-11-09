# Orchestrator

Your single point of entry when you do not want to think about which agent to ask, or when a piece
of work needs several of them. Orchestrator understands the request, splits it when needed, hands
each part to the agent best placed to do it, checks what comes back and gives you one answer.

## What it does

- Chooses the right agent for a request and hands it over with a brief that stands on its own:
  the goal, the task, the material, the result expected.
- Coordinates several agents on one piece of work, in the right order, passing the result of one
  to the next.
- Reads every reply as a reviewer: incomplete, contradictory or unverified work goes back once,
  then is reported to you as it is.
- Gives you one answer — the result first, then who did what and what is left —, never the
  replies pasted one under the other.
- Tells you when no agent fits, and which model of agent would.
- Remembers who is good at what and the preferences you gave it.

## What it needs

An imported agent arrives with no right beyond the defaults. On its Agent page:

| Setting | Why |
|---|---|
| **Can talk to other agents** (on by default) | Its whole job. You may narrow it to a list of agents. |
| **Memory** (on by default) | To learn who does what well, and your standing preferences. |

It needs nothing else: no system access, no web. The more specialised agents you have — Writer,
Researcher, Analyst, Developer… —, the more useful it is.

## How to use it

1. Ask Orchestrator as you would ask an assistant who knows the whole team.
2. For a larger piece of work, it tells you its plan in a few lines before starting.
3. You get one answer, with the paths of the files produced.

## Good to know

An agent that Orchestrator calls works with nobody in front of it: what would need your approval
there (a command of the machine, a publication) may be refused. Orchestrator then tells you which
agent to ask directly, with the request ready to paste. It never grants a right, to itself or to
another agent.
