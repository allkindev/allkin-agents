# Migrator

An agent that brings your agents from **OpenClaw** (formerly Clawdbot, Moltbot) or **NanoClaw**
into Allkin. Give it a zip of your old install: it leaves the secrets behind, rewrites each
agent's role and memory for Allkin, converts its competences, and hands you one archive per agent
to import, with a short list of what is left to do.

The aim is a good migration, not a perfect copy: what fits Allkin simply is carried over, the rest
is listed for you.

## What it does

- Recognises an OpenClaw or NanoClaw install (both NanoClaw layouts) and lists what it holds:
  agents, roles, memories, notes, competences, scheduled tasks, channels.
- Asks you, in one form, what to migrate.
- Writes one role per agent from its identity, soul and rules; keeps its durable facts as memory
  and its notes as files.
- Converts the competences into a repository you add in the Settings; the scripts that cannot run
  in Allkin are set aside with why.
- Lists the actions to create, the services and channels to connect, the rights to grant.

## What it needs

| Setting | Why |
|---|---|
| **Competence: Migrate agents** | Its whole method and its scripts; downloaded when the agent is created. |
| **Memory** (on by default) | To remember what it migrated. |

Nothing else: it works in its own folder. If you give it the right "Can schedule actions" and the
competence "Manage actions", it can also create the actions itself, each one approved by you.

## How to use it

1. On the old machine, zip the install:
   - OpenClaw: `cd ~ && zip -r openclaw.zip .openclaw -x '.openclaw/agents/*/sessions/*' '*/node_modules/*'`
   - NanoClaw: `zip -r nanoclaw.zip nanoclaw -x '*/node_modules/*' 'nanoclaw/data/sessions/*'`
2. Open a conversation with Migrator, attach the zip, ask it to migrate.
3. Answer its form, then follow its list: import each archive (the "+" of the agents list ›
   Import an agent), add the repository of competences, grant rights, connect services.

## Safety

Credentials, transcripts and the values of `.env` are never extracted; every token or key in the
configuration is replaced; an archive is refused while anything that looks like a secret remains.
The old platform's code is read, never run. Each imported agent arrives without any right and goes
through the identity card and its Verify button like every import. Delete the zip from the
agent's `Upload/` folder once done.
