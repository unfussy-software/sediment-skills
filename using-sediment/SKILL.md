---
name: using-sediment
description: Saves, finds, edits and links the HTML artifacts on the user’s Sediment shelf, through Sediment’s command line tool. Use when the user asks to save, file, shelve or keep a page, or to put it on the shelf; to find or pull up something on the shelf; to update or edit an artifact, its description or its tags; or to link to one.
---

# Using Sediment

Sediment keeps the user’s HTML artifacts on a shelf: a folder on their Mac,
and an app over it. Work with it through its command line tool alone. The
tool’s own help is the manual and always matches the installed version; this
skill only says which page to read, and what never to do.

## 1. Find the tool

Once per session, before the first command:

1. Run `command -v sediment`. If it prints a path, the tool is `sediment`.
2. Otherwise use the copy inside the app, by its full path, for the rest of
   the session: `/Applications/Sediment.app/Contents/Helpers/sediment`. If the
   app isn’t there, look for it by its bundle id with
   `mdfind "kMDItemCFBundleIdentifier == 'com.unfussysoftware.Sediment'"`
   and use `<app>/Contents/Helpers/sediment`. Go on with the user’s task at
   once.
3. When the task is done, offer to link the tool so the next session finds
   it, the link Sediment’s Settings ▸ Terminal gives the command for:
   `mkdir -p ~/.local/bin && ln -sf "<app>/Contents/Helpers/sediment" ~/.local/bin/sediment`.
   If `~/.local/bin` isn’t on `PATH`, offer as well to add it in the user’s
   shell profile. Ask before each of these writes; never make one unasked.
4. If no app is found, tell the user to install Sediment, and stop.

Wherever this skill says `sediment`, use what step 1 or 2 found.

## 2. Read the task’s page

| The user says | Read |
|---|---|
| save, file, shelve, keep, put it on the shelf | `sediment help saving` |
| find, pull up, open, what’s on the shelf | `sediment help finding` |
| update, edit, change, tag, rename, pin | `sediment help editing` |
| link to, a link to | `sediment help linking` |

“File it” means save it: a new artifact. Read a task’s page once per session,
then follow its steps in order. Don’t read it again for the next task of the
same kind, and don’t read the command pages unless a step needs a flag the
task page doesn’t show.

If the page ends by pointing at instructions for agents, run
`sediment help instructions` once this session, before you save or edit,
and follow the operator’s instructions alongside the tool’s pages. If no
page points at them, this shelf has none.

## 3. Never

- Never write to an artifact’s file in place, with an edit tool or a script.
  Change content through `sediment update`, as `sediment help editing` says.
- Never leave an `.html` file in the shelf folder: Sediment adds it to the
  shelf as a new artifact. Write drafts outside it.
- Never store an artifact’s path. Ask `sediment find` again each time; the id
  and the link are what last.
- Never guess an id from a title. Take it from `sediment find --json`, and
  ask the user when more than one artifact fits.
- Never retry after `content_changed` without a fresh `sediment find --json`:
  the artifact changed after you read it.

## 4. When a command fails

The error names a code and usually a hint: follow the hint. Exit 1 means
don’t retry; exit 2 means a retry may work. Run `sediment check` only when
the error and its hint don’t explain the failure, or the tool behaves unlike
its help. It diagnoses; it is never how a session starts.

If a task page is refused with `invalid_argument` and a hint listing the
pages the tool has, Sediment is older than 0.42.0. Tell the user to update it
with Sediment ▸ Check for Updates…, and for this session work from
`sediment --help` and the never list above.
