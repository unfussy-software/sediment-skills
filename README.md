# Sediment Agent Skills

Optional skills that teach an AI agent to work with Sediment, the shelf for
your HTML artifacts, through its command line tool. Each Sediment release
publishes them here from its own source, so a change made here is replaced
by the next release.

## Do you need them?

No. The tool's own help is the manual, and an agent with nothing but
`sediment --help` does every task right. An eval on a small model, three
rounds long, found no difference in correctness between agents with the
skill and agents without it.

What the skill buys is fewer steps: it names the one help page for each
kind of task, so an agent reads one or two pages instead of four or five
and spends fewer tokens. Install it when agents work on your shelf often,
or to have your shelf's instructions drafted for you.

## Skills

| Skill | What it does |
|---|---|
| `using-sediment` | Saves, finds, edits and links what’s on your shelf, through Sediment’s command line tool. |
| `writing-sediment-instructions` | Drafts your shelf’s instructions for agents from how you save and name your files and use the shelf, and writes only what you confirm. Runs only when you call it by name. |

## Install

### From the Command Line

    npx skills add unfussy-software/sediment-skills -g

`-g` installs them for you rather than for one project. Add `--list` to see
the skills first, without installing anything. It needs Node.js 22.20 or
later.

Each Sediment release is tagged here with its version. To install the skills
written for one release, name its tag:

    npx skills add unfussy-software/sediment-skills#v0.43.0 -g

### From Your Agent

Paste this to your agent, and it installs both skills and checks your Mac:

```text
Install two skills: fetch each of these, and save each unchanged
as a user-level skill under its own name, the folder in its URL,
wherever you keep skills.

https://raw.githubusercontent.com/unfussy-software/sediment-skills/main/using-sediment/SKILL.md
https://raw.githubusercontent.com/unfussy-software/sediment-skills/main/writing-sediment-instructions/SKILL.md

Then find the sediment command line tool as using-sediment's
first section says, run `sediment check`, and reply with only
these lines, each ending in ok or in what is wrong:

skills - ok
app    - ok
cli    - ok
shelf  - ok
```
