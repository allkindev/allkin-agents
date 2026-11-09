# Sentinel

Watches over your servers. Sentinel makes its rounds on the machines you give it, with commands
that change nothing, compares with last time, and tells you what needs attention before it becomes
an outage: the disk that fills, the certificate that expires in ten days, the backup that stopped
three weeks ago.

## What it does

- **Rounds**: disk, memory and load, services that must run, pending and security updates, a
  reboot required, certificates, backups, failed sign-ins and open ports, errors in the logs.
- **Trends**: it keeps each round's figures and tells you where they are heading — "`/var` at 91 %,
  full in about ten days".
- **A report sorted by urgency**: critical, warning, note; "all clear" is one line. Each finding
  comes with the exact command it proposes — which it runs only if you ask.
- **A sheet per machine**: what must run there, what is normal, your thresholds.
- **Incidents**: when something is down, a step-by-step diagnosis and a written report.
- **On its own** through Allkin's Actions: a round every morning or every week.

It never repairs on its own, never shuts a machine down, never reads a secret.

## What it needs

An imported agent arrives with no right beyond the defaults. On its Agent page:

| Setting | Why |
|---|---|
| **Services: your machines over SSH** | Create a service "Machine over SSH" per server (Services page), test it, then allow Sentinel to use it. The credentials stay in Allkin. |
| **System access: Read only** | To check the machine Allkin runs on, read-only, without approval. |
| **Can schedule actions** + competence **Manage actions** | For regular rounds. You approve each action it creates. |
| **Competences: Server health check, Incident report** | Its methods; downloaded when you give them. |
| **Memory** (on by default) | To remember your machines and your thresholds. |

### Rounds without you

Each command on a machine over SSH shows you a card; you may approve for the session, or save
patterns on Sentinel's page. A round **started by an action**, with nobody there, runs only on
machines whose service has the switch **"Act without approval"** on. That switch lets Sentinel run
commands there on its own: turn it on only for an **SSH account that can only read** on that
machine (an ordinary user without sudo, member of the groups that read the logs).

## How to use it

1. Create the SSH services and allow them on Sentinel's page.
2. Ask: "Make a first round." It discovers each machine, writes its sheet, and asks you once what
   it cannot observe: what must run, where the backups go.
3. Accept the action it proposes for regular rounds, or ask "make your round" when you want.
4. When it reports something, decide: it gives the command; you say yes or do it yourself.
