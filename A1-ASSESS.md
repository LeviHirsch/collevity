---
author: claude-opus-5.5
authored: 2026-10-03
source: ai-authored
kind: record
ratified_by: none
---
# A1 — Assess: the pieces

Step one of A3 on the `collevity` core. Levi's A3 note: "Assess: Get all the
pieces out there. Divide, break down, and compile the goals, resources,
requirements."

**How to read this**

- Text in quote marks is Levi's own words or a canon entry, with its source.
- A line marked **Reading** is Claude's interpretation. None of it is ratified.
- Nothing here is strategy. Strategy enters only in Levi's words.
- Counts are as of 2026-10-03 and will drift.

## At a glance

- The thing being built, in Levi's words (10/3): "the ultimate, revolutionary,
  tool suite that underpins graph implementation, user capture, personal
  management ui, task/project/process management, context retrieval."
- Five things carry the name `clv`, not three. Two more sit in the node
  sandboxes.
- The two node sandboxes arrived at the same folder layout and, after their own
  culls, kept the same two tools: make a node, and look under a node.
- The mini already runs a working form of identity and of the scope ladder
  (`clv whoami`, `clv env`).
- **Reading:** canon 40 left open "what is the LCD (lowest common denominator)
  that builds all of them?" The core in this repo is a candidate answer.
- **Reading:** canon 66's build order is frameworks and a lake, then skills,
  "then add tooling, then the UI wrapper". The lake and the skills exist. The
  tooling step is this repo.

## 1. Goals, in Levi's words

| When | Words |
|---|---|
| 10/3 | "the ultimate, revolutionary, tool suite that underpins graph implementation, user capture, personal management ui, task/project/process management, context retrieval." |
| 10/3 | "this our first step in the direction of being able to move toward levi's ultimate system. it's the personal management system, context management, file management, the whole shabang." |
| 10/3 | "there is the core of the tooling which is for managing the directory basically as context AND how the USER interacts with it all at once. there's sort of a downward connection/bridge at any layer." |
| 10/3 | "we need the core. And that is plenty if we just treat it as my ultimate tool. If all we ever accomplish is that I have the tool and am made for effective then that will be a win." |
| 10/3 | A tool suite that includes: "os for ai provenance. the credibility cascade and more." "custom scripting coordinated across global environment." "live app wrapper" "work orchestration. Agents and processes and data management" |
| 7/11 | "Collevity will become the ultimate orchestrator, life management system (all the way to a simple, elegant app UI), enterprise AI wrapper, and ultimate second brain with incredibly unique and inventive frameworks that are intellectually cohesive and data-unified (optimized for both humans and AIs)." |
| canon 28 | "Everything I do is about context retrieval. That is what collevity is made for." |
| canon 33 | "I'm tired of having a million apps for a million different things"; the ultimate goal is to "replace/wrap his primary file-management system". |
| canon 18 | To organize him; to visualize all his projects; to augment his thinking; "an intuitive, flexible tool for holistic life tracking and management". |
| org board T22 | "The critical things that we are developing are the wrapper around server entrances (things like identifying the user and routing to their environment, capturing their prompts/ideas/thoughts in a dropper of their own). We need to get the global environment working properly." |

## 2. Resources: what exists

### 2.1 The five things called clv

| | What it is | Where | State |
|---|---|---|---|
| 1 | Levi's launcher: `list` `add` `show` `rm` over his short commands | `~/.collevity/bin/clv` on the laptop | In use. In no repo. |
| 2 | The server's identity and scope tool: `whoami`, `env` | `~/.collevity/bin/clv` on the mini; source in the org-harness repo `bin/` | In use. Repo is behind the mini. |
| 3 | The fellows' sign-in kit: `setup` `login` `key` `update` `uninstall` | public tap `LeviHirsch/homebrew-tap`, folder `clv/` | In use by fellows. Stays in the tap (Levi 10/3). |
| 4 | Node tools, meant to become `clv node <verb>` | `_claude-node-sandbox/branch-6/bin/` | Prototype. Unratified. |
| 5 | A `/clv` coordination skill for one window of attention on one node | `_grok-node-sandbox/b3/clv-skill/` | Draft. Never installed. |

### 2.2 Levi's laptop

- `~/.collevity/`: `bin/` (the launcher), `user/bin/` (his short commands),
  `runtime/` (prompt capture, lake sync, entry-router), `cache/` (state and
  logs), `auth/` (credentials), `README.md`, `REGISTER.md` (credential
  pointers). A `config/` folder is named in the README as "later".
- `~/.zshenv` puts `user/bin` then `bin` on PATH. `~/.zshrc` still holds the
  folder-jump shortcuts, the `rm`/`ls` overrides and the Claude login shortcuts.
- Claude hooks in `~/.claude/settings.json` run the capture and router code from
  `~/.collevity/runtime`.
- Credentials sit in two places: `~/.config/collevity/` and `~/.collevity/auth/`.
- Skills load through links from `~/.claude/skills/` into the `levi-skills` repo.

### 2.3 The mini

- `~/.collevity/bin/`: `clv`, `clv-login` (the sign-in entry point),
  `clv-stamp`, `clv-tmux`, `clv-dwd` and five more Google tools, plus backup
  copies made on the box.
- `clv env` prints six scopes: global, creds, env, org, user, dir.
- One shared macOS account. The tools supply attribution, not separation.
- Tools are pushed from the laptop by `deploy-mini`; the mini holds no GitHub
  credential.

### 2.4 Products

| Product | What it does | Home |
|---|---|---|
| dropper-pipeline | capture, store, ingest: the lake format, lake sync, the prompt-capture hook | `collevity-tooling` |
| entry-router | a small-model read of every lake entry, kept in a parallel store | `02_CONTENT/entry-router` |
| mailman-protocol | short notes between live sessions | `collevity-tooling`, own board |
| records-filer | files dropped business records by content | `collevity-tooling` |
| claude-account-switcher | several Claude accounts at once, each in its own slot | `collevity-tooling` |
| iterative-draft-review | a rubric-and-rewrite loop for judged writing | `collevity-tooling` |
| the dev and ops board tool | one task board per product, in the repo | `~/.local/share/devops` |
| NascenTech's server harness | sign-in, identity, Google-as-a-person | `collevity-org-harness` (to be renamed) |

### 2.5 Skills

`checkin`, `orchestrate`, `session-save`, `schedule`, `task`, `transcribe`,
`research-report` (product); `reading-map`, `build-learning-project`
(personal); `dev`, `ops`, `spec`.

### 2.6 Data

- The lake: `03_TACTIC/_DATA/collevity_lake.jsonl`, with the router's reads
  beside it.
- Session packages: `03_TACTIC/claude_session-persistent-packages/`, each in
  three layers.
- The thread registry: `03_TACTIC/thread-registry.md`, kept by hand.
- Daily tracking logs; the Dropper spreadsheet; Google Calendar and Tasks.
- The canon: `collevity-canon/entries.jsonl`, 88 entries.

### 2.7 Running prototypes: the node sandboxes

Both are AI-authored and unratified. Levi declined every claim from the Claude
sandbox on 8/8.

| | Claude sandbox | Grok sandbox |
|---|---|---|
| Branches | seven (`branch-0` to `branch-6`) | four (`b0` to `b3`) |
| Tools that run | `new` `interview` `assemble` `validate` `assign` `packet` `plate` `complete` `spp` `address` | `peek` and `new` (the rest deleted in its own cleanup) |
| Worked examples | a `collevity` tree with entry-router, node-shape, orchestrator, a person | `haptic-launch` with one child |
| Its own verdict | 23 claims culled to 5; all 5 declined | "Honest core: `b2/` node tree + `peek` + `new`" |

The layout both arrived at:

```text
<node>/
  00_summary.md            what a parent reads
  _inputs/                 01_impetus · 02_resources/ · 03_references
  _outputs/                01_objective · 02_deliverables/ · 03_followon
  .collevity/              00_collevity · 01_rules · 02_method · 03_local/
  <child nodes>/           same shape
```

The Grok sandbox added `.collevity/coord/` for the state of one working
window (stage, what is selected, decisions, deferred items).

### 2.8 The design record

- Canon entries 1 to 88, ratified by Levi one at a time.
- A3 (Levi's note) and S3 (`01_STRATEGY/strategy-scope-spec.md`); S3 as one
  recursive operation, unratified, waiting on three questions.
- The 8/11 NascenTech node test and its four rulings.
- The org-harness prep pack and `AGENTS.md`.
- The credibility cascade document (5/25, "not yet operationalized").
- Protocols: credentials, session-save, orchestrator session.

## 3. Requirements: rules already set

**Ruled by Levi**

- The core has its own repo and board; each product keeps its own board, with
  one view over all; the tool is built apart from the server; the kit stays in
  the tap; the server tools stay where they are. (10/3)
- A node's address is its full path. No uid. A directory with `00_summary.md`
  is a node, held loosely. Projects are nodes and persist. (8/11)
- Session packages are events and are not nested inside entity nodes.
  (per the Claude sandbox ledger: "Settled by you")
- "don't add chaff": no scores or metrics without a specific need. (8/8, per
  the Claude sandbox ledger)
- Nothing enters the canon without his approval of the exact text. Paraphrase
  of his ideas is not offered back as canon. (canon README; 8/8)
- The kit "has to be agnostic ultimately": not everyone has macOS. (10/2)

**Canon**

- 27: only naturally existing files; no custom wrapped data types.
- 23 and 79: roll-ups and derived views are never sources of truth.
- 56: settings live in the folder and resolve by walking up.
- 81: the `.collevity` package carries folder-local and environment-global
  tooling; contain-versus-point is a mix.
- 4: one axis is things, the other is time.

**From operations**

- Never run hook or background code from iCloud. (9/28 outage)
- Secrets never sit in iCloud or in a repo; the register holds pointers only.
  (credentials protocol)
- A broken `clv-login` locks everyone out of the mini. (org-harness
  `AGENTS.md`)
- The tap is for installing only, and public installs carry no secrets. (10/3)

**Recorded in the org-harness `AGENTS.md` as decided** (whether each is
Levi's own ruling is not verified here)

- Read identity only through `clv whoami`.
- Never stamp an agent's write as the user's.
- Agents attach through the command line; any command-line agent can drive it.
- Work happens inside the node's folder; agent and person share it.
- Taking something in and breaking it down are different operations.
- Intent (Calendar, Tasks) and what happened (the log) stay separate records.
- Do not build `/strategy` or `/scope` skills.

## 4. Observations

### 4.1 From the two node sandboxes

1. **Both tracks use `.collevity` for the folder's own package and gave it the
   same inside:** rules (inherited inward), method ("what an agent assigned to
   this node is instructed by"), and local tools.
2. **The Grok track saw a name collision** between a folder's `.collevity` and
   `~/.collevity`, renamed it `_tools`, then went back.
   **Reading:** by canon 81 and Levi's 10/3 "core at any layer", they are one
   thing at two levels. Home is the outermost package.
3. **Both tracks planned `clv` as the way in.** Claude's tool says `node <verb>`
   "is what `clv node <verb>` becomes". Grok's gaps note lists "`clv` CLI
   subcommands" as "Skill-first; CLI later wraps same steps".
4. **Both tracks misread canon 73, and Levi corrected both.** It is the
   orchestrator handing a closed unit to the right agent or level without
   unpacking it. It is not a file format.
5. **Both tracks grew too many verbs and cut back.** Grok's closing note, under
   "Do not do next without a reason": "More verbs. More metrics. More
   sandboxes of sandboxes." It also recorded the critique that a tool needs "a real invoker
   (e.g. future A3 skill), not free-floating CLIs."
6. **Levi's order for the node work (8/6, quoted in the Claude sandbox):**
   "(1) `assemble` + (2) cell fill-state together … then (3) SPP-as-node
   (cheapest real test…), then (4) the orchestrating agent, which stays theory
   until 1–3 give it something concrete."
7. **Levi's split (8/8):** "separate the thinking approach into the
   population/architecture (how things are created, organized, sorted,
   maintained, versioned) as somewhat distinct from traversal/navigation
   (relativity-based movement, usage, work completion)."
   The built tools fell on both sides of it. Whether population is A3 and
   traversal is S3 is untested.
8. **Only the population side has ever been used on real material.** The 8/11
   NascenTech run used `new`, `assemble` and `address`. No unit of work has
   ever been handed to an agent.
9. **A node can serve as an agent's instructions.** The Claude sandbox maps
   who, why, what for, rules and method onto the node's files and launches an
   agent with its working folder set to the node.
   **Reading:** this is a drafted mechanism for Levi's "downward… isolation of
   agents and such for context isolation".
10. **Addresses exist in prototype and nothing uses them.** Entities take a
    path; events take a time. As of 8/8 the router had flagged 769 lake entries as
    alluding to something, with nothing to resolve to.
11. **A session package can be shown as a node without moving it.** The run
    found the package format records what was produced and what it triggers,
    but not why the session was held or what it was for.
12. **Both tracks lean toward generating the thread registry from the node
    tree** instead of keeping it by hand. Undecided.
13. **The sandbox documents already carry provenance marks** in their headers
    (`source: ai-authored`, `ratified_by: none`).
    **Reading:** a working, informal case of canon 38.
14. **The tracks were independent in one direction only.** The Grok track read
    the Claude sandbox (`CLAUDE-COMPARE.md`). Its own lesson: "Independent dual
    sandboxes create false canon when one track's verbs are read as user
    intent."

### 4.2 From the org-harness

1. **The scope ladder already runs.** `clv env` on the mini resolves global,
   creds, env, org, user and dir. The drafted rule beside it (8/12, Claude,
   not ruled): state lives at the narrowest scope; reads merge upward; writes
   land at the narrowest.
2. **Identity already has a one-person mode.** `clv whoami` falls back to a
   self-declared name read from `~/.collevity/user/principal`.
3. **Four words are fixed there:** principal (who signed in), actor (who
   acted, maybe an agent), subject (whose Google account), method (how
   identity was established). "none" is an allowed, labelled state.
4. **The laptop's capture hook marks every entry's author as "user" without
   checking who wrote it.** The org board names this as a defect (D-002) to
   avoid carrying over.
5. **The server keeps surfacing needs that are general, not NascenTech's:**
   - land in your own space at sign-in, with a welcome that says what you can
     do (T106, T120);
   - tell the AI who it is serving (T108);
   - drop a thought without the AI (T110);
   - a session id per sign-in, so two sessions do not collide (T41);
   - a thin log of who did what (T11);
   - rules the AI cannot override (T113);
   - the same capture for Claude and Grok, skipping agent calls (T59);
   - send a person's server captures back to their own lake (T124);
   - a per-person or per-team AI account (T107);
   - people changing their own setup (T151).
6. **The general engine is parked on that board as "Later"** (T135): nodes as
   the work surface, retrieve and promote, threads and assignment, the
   orchestration loop, agents, saved sessions.
   **Reading:** these are core-shaped. Which board holds them is Levi's call.
7. **The repo drifted behind the machine it deploys to.** Tools were edited on
   the mini, and a deploy would now roll the server back (T91).
   **Reading:** this is what a per-part install record is for.
8. **Many "Decision:" lines on that board were AI-drafted** on 8/12 to 8/16
   and marked on 10/2 as "proposals, not Levi's rulings".
9. **Out of scope there, by its own `AGENTS.md`:** a client UI (a read seam
   only), a graph database, an access-control product, a Dropper rewrite.
10. **Levi's questions on that board that the core also has to answer:**
    "Which skills/capabilities do we want them to know they have? How will
    they know they have them?" and his finding that a list of skills "doesn't
    actually tell them how to do their work".

### 4.3 From the strategy record

1. **The component roster (canon 17):** capture (Dropper), store (collake),
   ingest and extraction, Aggregator, Retrieval, Orchestrator, and Vitrix for
   output. "Non-exhaustive."
2. **The lake is the spine (canon 11),** and "everything is an entry" (canon
   10). From the lake "you can recreate the entire directory setup" (canon 37).
3. **File management is the level of work (canon 44):** creating a project,
   thread or folder "stays in line with normal directory management plus the
   dropper".
4. **How context moves (canon 71 to 74):** it inherits inward; problems report
   outward; the orchestrator passes closed units between levels; escalation is
   ordinary.
5. **What S3 taught (7/11, AI-compiled, unratified):** spec works and is
   proven twice; scope decisions have no home; strategy cannot be synthesized
   by an AI and has to be drawn from Levi and ratified.
6. **Personal management runs today as skills over surfaces:** the daily log,
   the thread registry, Google Tasks, the plan calendar, the ACTUAL calendar,
   the session-package lake. Skills offer at the edges and never call each
   other.
7. **Levi runs Claude and Grok on the same brief and compares** (node
   sandboxes, org-harness prep, minimal-orchestrator).
   **Reading:** the core cannot belong to one AI tool.
8. **Two hubs were expected to meet.** The 7/11 thread map (AI-written)
   records Levi's working model: the Collevity hub and the orchestration and
   dev-infra hub "will **converge**; developed separately for now".
   **Reading:** this repo is where they meet.
9. **The same map calls the storage and data model "The unsolved core":**
   "rigid-yet-flexible, multi-dimensional dependencies.""

### 4.4 Against the five capabilities Levi named

| Capability | Exists today | Missing, by the record |
|---|---|---|
| **Graph implementation** | Canon 4, 6, 7, 12 (nodes, weighted edges, four kinds of dependency). The node layout, in two prototypes. An address index, in prototype. | Edges: nothing draws or weighs them. Nothing reads the addresses. The storage model. |
| **User capture** | The Dropper, the prompt hook, the lake, lake sync, the router's reads. All on the laptop. | A thought-drop command without the AI. Honest author marks. A file dropper (canon 46). Live processing of each drop (canon 29). Any capture on the mini. |
| **Personal management UI** | Skills over surfaces. Two interface concepts (canon 55, 68). A whole node tree as JSON, with no view. A terminal board viewer. | Any interface. Canon 66 puts it last. |
| **Task, project and process management** | Dev and ops boards in at least four repos. The thread registry. `/orchestrate`. Session packages. S3 at spec level. | The one view over boards (ruled 10/3). Assignment. A registry that is derived. Scope's home. The S3 loop. |
| **Context retrieval** | Canon 7, 28, 39. The router's reads. The top layer of each session package. The context manifest habit. | Retrieval itself. Handing a closed unit to an agent has never been done. Promotion has nothing to promote to until addresses are used. |

## 5. Questions on the record that are Levi's

- Is "a small core plus installed parts" the ruling on shape? (board T2)
- What `clv update` does, and what `clv uninstall` removes. (board T3)
- Which of the five `clv`s keep the name.
- Whether the general engine parked on the org board moves here.
- Population and traversal: do they map to A3 and S3? (8/8)
- How time sits in a node. (Claude sandbox)
- May an agent assign work, or only propose it? (Claude sandbox)
- `02_resources/` and `02_deliverables/` as subfolders: his reservation,
  carried since 8/6.
- The thread registry: generated from the tree, or kept beside it.
- An events pool per root, and how it sits against git history. (8/11,
  provisional)
- S3's three questions: is the top inventing or decomposing; is a frame the
  same thing as an entry; is planning the same walk as doing.
- Scope order and "read upward, write to the narrowest": drafted 8/12, not
  ruled.

## 6. What was read, and what was not

**Read:** all canon entries; Levi's A3 note; both node sandboxes' documents and
tool headers (the Grok one on Levi's instruction, 10/3); the 8/11 node-test
notes in memory; the org-harness `AGENTS.md`, `bin/`, the board and about
forty task bodies, and the Claude prep pack; `01_STRATEGY` (S3 lessons, thread
map head, protocols list); the suite surfaces map; product READMEs; the laptop
and mini `.collevity` listings.

**Not read:** the Grok fork of the org-harness prep (not named by Levi); the
filled node files inside each sandbox branch; most org-harness task bodies;
the lake itself, beyond searches; the Apple Notes export beyond the A3 note;
the fable-protocol and minimal-orchestrator internals.
