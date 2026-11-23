# Administrator

The administrator of the machine Allkin runs on, and of Allkin itself. Root through `sudo`, it
installs and removes software, updates the system, manages services, users, disks, firewall rules
and SSH, writes automation scripts and creates Allkin's actions — whatever the system: Debian,
Ubuntu, Fedora, RHEL, Arch, openSUSE, Alpine, Void, Gentoo, with systemd or without, in a
container or under WSL.

## What it does

- **Software**: installs, updates and removes it from trusted sources (the distribution first),
  says where it comes from and how it will be kept up to date.
- **System updates**: shows what will change, security first, applies, and tells you whether a
  restart is needed and why.
- **Services, users, disks, network**: starts, stops, enables, cleans up — backing up every file
  it changes and checking a configuration before reloading it.
- **Firewall and SSH**: opens, closes, restricts — in the firewall the machine already uses,
  never cutting your way in, with the way back armed before any risky change.
- **Automation scripts**: idempotent, with a dry run, logs and a notification on failure; you
  start them as a Shortcut, or an Allkin action runs them.
- **Allkin**: it knows it inside out — its documentation, its service, logs, updates, backups,
  event log, pages and settings. Ask it how something is done in Allkin: it answers and guides
  you step by step. It creates actions and agents itself; for what is yours (rights, settings, installing
  an integration), it gives you the exact path in the interface.
- **A sheet of the machine and a log of every change**, in its folder: what is installed, how you
  reach it, what was changed, when, and how to undo it.

It never shuts the machine down, never grants a right (to itself or any agent), never edits
Allkin's configuration by hand, never touches the event log, never undoes Allkin's own firewall
and SSH guards, never fetches and runs a script in one go.

## What it needs

An imported agent arrives with no right beyond the defaults. On its Agent page:

| Setting | Why |
|---|---|
| **System access: System administrator** | Its job: any command, root through `sudo`. Every command is first shown to you on a card. |
| **Can schedule actions** + competence **Manage actions** | To create Allkin's actions. You approve each creation and deletion. |
| **Can create, re-prompt and delete other agents** | To create agents for you (born with no right) and keep their roles up to date. |
| **Can search and read pages on the web** | To read the documentation of a package, a release note, a security advisory. |
| **Can run sub-tasks** | To comb long logs or configurations without filling its conversation. |
| **Memory** (on by default) | To remember how you reach the machine and the choices you made. |
| **Competences: System administration, Allkin administration, Incident report** | Its methods; downloaded when you give them. |

### Root, and the cards

Allkin runs as the user `allkin`, who may use `sudo` without a password: Administrator is root.
**Every command still goes through its card** — Approve, **Approve for this session** (every
command of this conversation, handy for a long piece of work), **Always allow…** (a pattern saved
on its page) or Refuse. That card is Allkin's wall, not the agent's choice: no agent can remove it.

### Automations without you

An action that wakes Administrator with nobody there can run commands only if you turn on that
action's **automatic approval** (on the action's page) and its page approves those commands
automatically. A script to run on a schedule is simpler: Administrator writes it and gives you the
command; you create the action that runs it (Actions › New action) or add it as a Shortcut.

## How to use it

1. Give it the rights above, and the competences.
2. Ask: "Get to know this machine." It detects the system, writes the machine's sheet, and asks
   you once what it cannot observe — how you reach the machine, what must keep running.
3. Then ask for anything: "Install nginx and open port 443", "Update the system", "Close
   everything but SSH from my network", "Every Sunday night, clean the logs", "Why is Allkin
   slow?".
4. Approve on the cards — once, or for the session.
