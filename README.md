# Allkin Agents

The **models of agents** of [Allkin](https://github.com/allkindev/allkin): one folder per agent,
what an export of an agent holds, unzipped — its role, its card, its picture, what it depends on.
Allkin lists them in its "New agent" window ("Or start from a model") and installs one through the
identity card of an import: the user reads what it is, what it asks for and what it depends on, may
have it verified, then imports it. **A model grants nothing**: whatever its card says, the agent
arrives without any right; the user grants them from its settings.

```
agents/<id>/
├── agent.json          the card: name, version (1.0.N), description, author, locales,
│                       and the rights the agent asks for (granted by the user, never by the import)
├── CLAUDE.md           the role — the real content of the agent, written for the model, in English
├── README.md           for the user, with README-FR.md, README-ES.md, README-DE.md
├── dependencies.json   optional: the competences and services it uses (installed on their own
│                       terms: a competence is downloaded when the agent is given it)
├── memory.json         optional: the facts it starts with
└── avatar.png          its picture, 512 px (jpg accepted too): every model ships with one
```

The simplest way to write one: export an agent from its Agent page in Allkin, unzip the `.allkin`
archive into `agents/<id>/`, add the README files, then run the catalogue.

| Model | What it is for |
|---|---|
| `orchestrator` | Your single point of entry: it understands a request, hands each part to the agent best placed to do it with a complete brief, checks what comes back and gives you one answer. |
| `developer` | A software developer that works like Claude Code: it explores a code base before touching it, plans, changes little, verifies by running the tests and the build, and reports plainly. |
| `writer` | A writer and editor that hands over finished text: it settles the reader and the purpose before writing, plans, drafts, revises in separate passes, checks every fact, and learns your voice. |
| `researcher` | Finds out and keeps watch: a question answered by a dated brief whose every claim has its source, and a subject followed week after week, reporting only what is new. |
| `analyst` | Makes tables speak: it checks what a CSV or Excel file really contains, computes every figure with scripts — never in its head — and hands over a short note with the table and the chart that prove it. |
| `secretary` | Your administrative assistant: letters and e-mails ready to send, minutes of meetings, Word and Excel documents filled in, and a list of everything that is waiting, brought back at the right time. |
| `project-manager` | Turns a goal into a plan and keeps it true: milestones, tasks with an owner and a date, risks named early, and a regular status that says where the project really stands. |
| `community-manager` | Runs your social networks like a professional: an editorial line, a calendar, posts adapted and checked for each network, comments triaged and answered in your voice, real figures. Nothing is published without you. |
| `sentinel` | Watches over your servers: disk, memory, services, updates, certificates, backups and security checked with read-only commands, compared with last time, reported before they become an outage. |
| `tutor` | A patient private teacher: it finds out what you already know, explains at your level, makes you practise, checks that you really understood, and brings back what you learnt before you forget it. |
| `migrator` | Brings your agents from OpenClaw or NanoClaw into Allkin: reads an archive of the old install without its secrets, rewrites each agent's role and memory, converts its competences and hands back archives to import with a short to-do list. |

## Layout

Every repository for Allkin has the same layout, whatever it holds — one of these folders, or several:

```
catalogue.json          written by scripts/catalogue.mjs, never by hand (signed: catalogue.json.sig)
scripts/catalogue.mjs   checks every entry and writes the catalogue
agents/<id>/            a model of agent: agent.json, CLAUDE.md, README.md…
plugins/<id>/           an integration: plugin.json, its code, README.md…
skills/<id>/            a competence: SKILL.md, skill.json, README.md…
services/<id>/          a declarative service: service.json, README.md…
```

The code keeps the folder names of before (`plugins/`, `skills/`); the user reads integrations and
competences. An `id` is the folder name: lowercase letters, digits and dashes.

## Versions: `1.0.N`

Every entry carries a version of the form `1.0.N`: three numbers, the first two fixed, `N` an
integer without a leading zero. **Every change** to an entry (code, manifest, README, picture) raises
`N` by one, in the same change — Allkin offers an update only when the catalogue is ahead of the
installed version, and compares number by number (`1.0008` would read as `1.8`).

## The catalogue

```
node scripts/catalogue.mjs            # checks every entry, writes catalogue.json and signs it
node scripts/catalogue.mjs --check    # checks without writing (exit 1 on a difference)
node scripts/catalogue.mjs --unsigned # writes without signing: for a repository that is not Allkin's
```

The catalogue lists every file of every entry with its size and SHA-256 digest: an Allkin refuses
to install an entry whose files do not match. The catalogues of Allkin's four repositories are
signed with the owner's Ed25519 key (`~/.allkin-signing/catalogue.key`, never in a repository);
Allkin carries the public half and reads nothing from one of its repositories whose signature is
missing or wrong. `catalogue.json` and `catalogue.json.sig` are always committed together. The
owner publishes with `~/allkin-scripts/git_commit_tools.sh`, which raises the versions, regenerates
and signs the catalogue, commits and pushes.

## Your own repository

Anyone can make a repository Allkin reads: the same layout, this very `scripts/catalogue.mjs` run
with `--unsigned`, and the page of the repository pasted in Allkin under **Settings › General ›
Repositories**. What comes from it is shown as "not checked by Allkin". Allkin's own sheet
"Create a repository for Allkin" (the button of that section) says it all, step by step.

Every text shown to the user exists in the four languages of Allkin (en, fr, es, de).
