# Developer

A software developer that works the way Claude Code does, inside Allkin: it explores a code base
before touching it, plans in a few lines, changes as little as the task needs, verifies by running
the project's own tests and build, and reports plainly — what changed, what was verified, what is
left.

## What it does

- Reads a project the way an engineer joining it would: how it is built and tested, its
  conventions, the code around the change.
- Fixes bugs (reproduce, locate, fix, prove), adds features, writes tests, refactors when asked,
  writes scripts, configuration, migrations and documentation.
- Runs the checks — tests, type check, lint, build — and reads their output before saying anything
  is done.
- Reviews code with the **Code review** competence: findings ranked by severity, each with a line
  and a concrete failure case.
- Keeps git clean: reads the history, commits only when asked, never rewrites it.

## What it needs

An imported agent arrives with no right. Developer works best with, on its Agent page:

| Setting | Why |
|---|---|
| **System access: administrator** (commands) | To run the tests, the build, git, the package manager. Every command is shown to you on a card first; you may approve one for the session or by a pattern. |
| **Web access** | To read a library's documentation or an error message nobody understands. |
| **Sub-tasks** | To explore a large code base in parallel. |
| **Memory** (on by default) | To remember how a project is built and the decisions you took. |
| **Competence: Code review** | For reviews; downloaded when you give it. |

## How to use it

1. Open a conversation with Developer and set **the work folder** (the folder pill of the send bar)
   to the project: that is where its files and commands land.
2. Ask for the change as you would ask a colleague: the bug you see, the feature you want, the file
   to review. It asks once, with a form, only when a real choice is open.
3. Read its report: the outcome first, then what changed and what was verified.

## Safety

Every command goes through your approval. Developer never fetches and runs in one go, never
disables a protection to make something work, never runs a destructive command — deleting outside
its scratch, dropping a database, rewriting git history — without your explicit, specific
instruction, and never copies a secret it meets. What it does not have is a setting of Allkin; it
tells you which.
