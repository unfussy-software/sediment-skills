---
name: writing-sediment-instructions
description: Drafts, confirms and writes the instructions on the user’s Sediment shelf, their preferences for how agents save, find, edit, link and tag there, from how the user saves and names their files and uses the shelf, and a few questions. Runs only when the user calls it by name. Never load it on your own, and never offer it.
---

# Writing Sediment Instructions

A shelf’s instructions are one file, `INSTRUCTIONS.md`, kept in the shelf:
the user’s preferences for how agents use it, read by every agent before it
saves or edits. Run this only when the user calls it by name; never offer it.

## 1. Find the tool

Run `command -v sediment`. If it prints nothing, use
`/Applications/Sediment.app/Contents/Helpers/sediment`, or
`<app>/Contents/Helpers/sediment` where
`mdfind "kMDItemCFBundleIdentifier == 'com.unfussysoftware.Sediment'"` finds
the app. If no app is found, tell the user to install Sediment, and stop.
Wherever this skill says `sediment`, use what you found.

## 2. Read what is there

Run `sediment help instructions`. It ends with THIS SHELF: the hash to write
with, then the current file, if there is one. Keep both.

## 3. Gather, in this order

1. Your session records. Search them for every time an HTML file was saved
   or kept, through `sediment` or any other way (written to a folder,
   renamed, moved), and the replies around it; never read a whole session.
   Note names, titles, descriptions, how files were grouped, and above all
   where the user corrected these.
2. Your memory notes: the parts about naming, saving, keeping and finding
   files, not only the lines that mention Sediment.
3. Your global rules: the same parts.
4. `sediment tags`, once: the shelf’s tags, each with its meaning.
5. Last, the user: ask only about what the first four leave open.

Don’t survey the shelf’s artifacts. Say in one line which source you
couldn’t read, such as past sessions you have no access to, and finish from
the rest. Take only habits about keeping files: never a path, a secret or
anything else from your sessions.

## 4. Draft

Polish each preference into a short line under the heading of its task, in
this order: `## Saving`, `## Finding`, `## Editing`, `## Linking`,
`## Tags`. Carry a habit over in the shelf’s terms, never as the path or
folder it came from: a folder per project becomes a tag per project, dates
at the front of file names a line about names and titles, a note of what
each file holds a line about descriptions. Leave out a heading with nothing
under it, and leave out:

- How a page is made: its look, content or structure.
- When to use Sediment, such as “save HTML artifacts to the shelf instead of
  publishing them”: an agent reads this file only once it is using the shelf.
- Anything the tool’s help already says, such as what never to do.

If there is a file, merge into it: keep each of the user’s lines word for
word unless the user changes it.

## 5. Show it

- No file yet: show the whole proposal, section by section.
- A file: show only what you would add, change or remove, under its heading.
  Show a finding that contradicts a line beside that line, and let the user
  choose.
- Mark a line drawn from a habit, not a correction or the user’s own words.

Write only what the user confirms; if they confirm nothing, write nothing.

## 6. Write it

Never write `INSTRUCTIONS.md` yourself, and never draft in the shelf folder.
Write the whole new file outside it, then hand it over with
`sediment instructions`: `--content` names that file, and `--expected-hash`
takes the hash step 2 printed. If the reply is `content_changed`, the file
changed after you read it: go back to step 2, merge, and show what is new.
Never send the same file again.

## 7. Offer once to tidy

Once the file is written, offer once to remove the rules now in it from your
memory notes and global rules, each listed with its file and removed only on
approval. Offer only a rule about the shelf alone. Keep a rule that also
covers files or pages that never go on the shelf, and every rule about when
to use Sediment, and say why: the first still binds work off the shelf, and
the file is read only once an agent is already using it.
