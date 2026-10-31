# Sediment agent skills

Optional skills that teach an AI agent to work with Sediment, the shelf for
your HTML artifacts, through its command line tool. Each Sediment release
publishes them here from its own source, so a change made here is replaced
by the next release.

## Install

    npx skills add unfussy-software/sediment-skills -g

`-g` installs them for you rather than for one project. Add `--list` to see
the skills first, without installing anything. It needs Node.js 22.20 or
later.

Each Sediment release is tagged here with its version. To install the skills
written for one release, name its tag:

    npx skills add unfussy-software/sediment-skills#v0.43.0 -g

## Skills

| Skill | What it does |
|---|---|
| `using-sediment` | Saves, finds, edits and links what’s on your shelf, through Sediment’s command line tool. |

## Without Node.js

Paste this to your agent:

```text
Install the using-sediment skill: fetch
https://raw.githubusercontent.com/unfussy-software/sediment-skills/main/using-sediment/SKILL.md
and save it unchanged as a user-level skill named using-sediment, wherever
you keep skills. Then find the sediment command line tool as the skill's
first section says, run `sediment check`, and reply with only these lines,
each ending in ok or in what is wrong:

skill - ok
app   - ok
cli   - ok
shelf - ok
```
