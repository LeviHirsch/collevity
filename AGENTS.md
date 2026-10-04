# collevity

The core of Levi's tool: the `clv` command and the `.collevity` package.

Provisional. Written 2026-10-03 when the repo was created, from what Levi said
that day. The full quoted record is task T152 on the org-harness board
(`02_CONTENT/collevity-org-harness`). Correct this file freely.

## What this is, in Levi's words (2026-10-03)

- "this our first step in the direction of being able to move toward levi's
  ultimate system. it's the personal management system, context management,
  file management, the whole shabang."
- "there is the core of the tooling which is for managing the directory
  basically as context AND how the USER interacts with it all at once. there's
  sort of a downward connection/bridge at any layer."
- "the basic core is the same between client and enterprise. More like just
  the specific content installed."
- "we need the core. And that is plenty if we just treat it as my ultimate
  tool. If all we ever accomplish is that I have the tool and am made for
  effective then that will be a win."

## Ruled by Levi (2026-10-03)

- This repo is the source, and it is named `collevity` ("I think collevity").
  It is not part of `collevity-tooling`: "too core to be in collevity tooling".
- The tool is built separately from the NascenTech server: "the dev of the
  tool should be separate." The server is where to "test by doing"; what it
  teaches comes here as ideas.
- Each product keeps its own board and repo, with one view over all of them
  ("B makes sense."). The view is not built.

Not ruled, his label "thinking out loud": a level connects down to what it
contains (agents on a person's install; people and agents at an org) and up to
the level that contains it. Versioning is a later question.

## Design seeds (canon, ratified by Levi, binding)

`00_COLLEVITY/collevity-canon/entries.jsonl`: entry 15 (every folder is its own
app), entry 56 (settings live in the folder and resolve by walking up to parent
folders), entry 81 (the `.collevity` package carries folder-local and
environment-global tooling; contain-versus-point is a mix).

## What is not here yet

No code has moved. As of 2026-10-03 the three programs called `clv` still live
where they were:

- Levi's laptop launcher: `~/.collevity/bin/clv`, in no repo.
- The server's identity tools: `bin/` of the org-harness repo.
- The fellows' sign-in kit: `clv/` in the public tap `LeviHirsch/homebrew-tap`.
  The tap is for installing only; released install scripts go there from here.

## Git layout

The working folder is in iCloud. The real git folder is
`~/dev/collevity/collevity.git`, and `.git` here is a pointer file to it. Never
turn `.git` back into a folder and never delete the external git folder:
iCloud corrupts live git folders.

Never run hooks or background jobs from this folder. Installed copies run from
`~/.collevity` (local disk); iCloud can evict a file mid-run and deadlock it.

`CLAUDE.md` is a symlink to this file.
