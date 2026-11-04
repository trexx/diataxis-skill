# Diátaxis skill for Claude Code

A reusable [Claude Code](https://claude.com/claude-code) skill that applies the
**[Diátaxis](https://diataxis.fr) documentation framework** whenever you write, review,
structure, or improve technical documentation.

Diátaxis (by Daniele Procida) identifies **four kinds of documentation**, each serving a
distinct user need:

| Type | Serves | Answers |
|------|--------|---------|
| **Tutorials** | learning (study) | "Can you teach me to…?" |
| **How-to guides** | goals (work) | "How do I…?" |
| **Reference** | information (work) | "What is…?" |
| **Explanation** | understanding (study) | "Why…?" |

The skill helps Claude **classify** content by the need it serves (using the Diátaxis
"compass"), **keep the four types from bleeding into each other**, and **write, name, and
organise** each kind correctly.

## Overview

### What's in here

```
diataxis/                     <- the skill (drop this into any .claude/skills/)
  SKILL.md                    <- entry point: compass, the four types, workflows, quality gate
  references/
    four-types.md             <- full per-type principles, language, and the two boundary deep-dives
    checklists.md             <- authoring + review checklists and a "mixing types?" diagnostic
    templates.md              <- copy-paste skeletons for each type and for landing pages
```

## Usage

### Install

Copy (or clone/symlink) the `diataxis/` folder into a skills directory. Keep the folder
named `diataxis`.

**For yourself, everywhere (user-level):**

```bash
cp -r diataxis ~/.claude/skills/diataxis
```

**For a specific project / your team (committed to that repo):**

```bash
cp -r diataxis /path/to/your-docs-repo/.claude/skills/diataxis
```

Then commit `.claude/skills/diataxis` in that repo so teammates get it too.

**As a git submodule** (to track updates):

```bash
git submodule add <this-repo-url> .claude/skills/diataxis
```

Restart Claude Code (or start a new session) so the skill is picked up.

### Use

- **Automatic:** the skill's description triggers it whenever you ask Claude to write,
  review, restructure, or diagnose documentation.
- **Explicit:** invoke it by name with `/diataxis`.

Try: *"Write docs for this feature using Diátaxis"*, *"Is this page a tutorial or a
how-to?"*, or *"Audit our docs against Diátaxis."*

## Development

The skill is plain Markdown with no build step: `diataxis/SKILL.md` is the skill itself, and `diataxis/references/` holds the reference material it points to. Edit the files in place; an installed copy picks up changes if it is a symlink, otherwise copy the folder again (see Install).

## Licence

The Diátaxis framework is created by **Daniele Procida** and published at
<https://diataxis.fr> under **[CC-BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/)**.
This skill distils that framework for use inside Claude Code and is distributed under the
same **CC-BY-SA 4.0** licence (see `LICENSE`). It is a derivative work, not the official
Diátaxis documentation.
