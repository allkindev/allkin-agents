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
└── avatar.png          optional: its picture (jpg accepted too)
```

The simplest way to write one: export an agent from its Agent page in Allkin, unzip the `.allkin`
archive into `agents/<id>/`, add the README files, then run the catalogue.

| Model | What it is for |
|---|---|
| `developer` | A software developer that works like Claude Code: it explores a code base before touching it, plans, changes little, verifies by running the tests and the build, and reports plainly. |

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
