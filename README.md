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
| `sediment-shelf` | Saves, finds, edits and links what’s on your shelf, through Sediment’s command line tool. |
| `sediment-instructions` | Drafts your shelf’s instructions for agents from how you save and name your files and use the shelf, and writes only what you confirm. Runs only when you call it by name. |

## Install

### From the Command Line

    npx skills add unfussy-software/sediment-skills -g

`-g` installs them for you rather than for one project. Add `--list` to see
the skills first, without installing anything. It needs Node.js 22.20 or
later.

### From Your Agent

Paste this to your agent:

```text
Install the two skills in
https://github.com/unfussy-software/sediment-skills
as user-level skills. Then find the sediment
command line tool as sediment-shelf says,
run `sediment check`, and tell me what it
reports.
```
