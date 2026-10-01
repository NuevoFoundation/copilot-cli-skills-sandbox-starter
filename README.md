# Build the Nuevo Foundation delivery SKILL

**GitHub Universe 2026, BLD1487S | Nuevo Foundation**

**The goal of this lab is to build a SKILL and use it in everyday development.**
Product managers should not have to chase developers for progress, and developers
should not have to reconstruct their work for a status update. Teach GitHub Copilot CLI to
handle issue tracking and documentation as you build, so you can focus on
features and fixes and make your impact easier to see.

You provide a comprehensive prompt. GitHub Copilot CLI creates the `issue-lifecycle` SKILL.
Then try normal feature requests and watch it track, build, check, and document
the work. The ten PM briefs are optional practice, one at a time.

Open **[lab-guide.html](lab-guide.html)** for the offline-friendly guided view.
Open **[index.html](index.html)** for the on-brand website canvas. Both work
without a server or package install. There is deliberately no active `SKILL.md`
in `.github/skills/issue-lifecycle` yet; your prompt asks GitHub Copilot CLI to create it.
Facilitators: use **[FACILITATOR.txt](FACILITATOR.txt)** for the exact clock,
separate presenter setup, bounded demo prompt, and recovery decisions.

## The 45-minute session

| Time | Block | Outcome |
| --- | --- | --- |
| 0-5 | Welcome | Understand the NF problem; begin managed-account sign-in |
| 5-20 | Topic + demo | Understand nine concepts; see the actual NF SKILL and its evidence |
| 20-24 | Build + personalize | Paste the prompt; GitHub Copilot CLI creates the SKILL |
| 24-27 | Build + personalize | Check discovery and try a normal feature-preview request |
| 27-30 | Build + personalize | Track the SKILL's introduction; add and preview one local rule |
| 30-35 | Build + personalize | Review, publish, and finish with actual evidence |
| 35-40 | Build + personalize | Start one optional PM challenge, or consolidate the core outcome |
| 40-45 | Wrap | Share the evidence and choose a workflow to take home |

Setup is budgeted, not invisible. Begin sign-in during the welcome and allow
the first lab minutes for stragglers. If access takes longer, use the recovery
lane instead of sacrificing the skill-building outcome. Stop new work at 40.

## 1. Confirm your assigned repository

The room uses **Enterprise Managed Users (EMU)** and imported materials.
Use the provided managed account, host, and per-seat writable repository.
Do not fork or clone the public NF repositories from a room account, switch to
personal credentials, or work in another attendee's repo.

Start GitHub Copilot CLI from the local assigned repository. In a terminal:

```powershell
gh auth status
git remote -v
gh repo view --json nameWithOwner,url,hasIssuesEnabled,viewerPermission
```

If sign-in is needed, follow the facilitator's host-specific `gh auth login`
instructions. Inside GitHub Copilot CLI, use `/login` if needed. These are separate access
checks. Never put tokens or passwords in chat or files.

Confirm the exact assigned URL, Issues enabled, and `WRITE`, `MAINTAIN`, or
`ADMIN` access. Use that full URL on `gh --repo` commands; API verification uses
its matching `--hostname`. Public NF issue numbers in the demo are evidence,
**not your lab target**.

The static pages, brief text, source snapshots, and SVG assets are local.
Hosted GitHub Copilot CLI still needs approved model-service connectivity; GitHub changes
need the assigned host. "No public-repo access" is not the same as "no network".

## 2. Ask GitHub Copilot CLI to build the SKILL

Open the [comprehensive prompt](lab-guide.html#build-prompt), select **Copy prompt**,
and paste it into **GitHub Copilot CLI chat**, not your shell.
You do not need to create or assemble the file yourself.

The prompt explains the team's problem and tells GitHub Copilot CLI to create
`.github\skills\issue-lifecycle\SKILL.md` using the six supplied local parts.
Those parts reconstruct the real NF core. GitHub Copilot CLI checks the result and explains
the checkpoints below. This first request only creates the local SKILL;
it does not authorize changes to GitHub or the website.

| Part | Find this idea before moving on |
| --- | --- |
| `01-discovery.txt` | `name` and `description`: what it is and when to use it |
| `02-target-and-gate.txt` | Confirm the repo, permissions, scope, and definition of done |
| `03-start.txt` | Reuse/open an issue, apply `in progress`, then stop |
| `04-work.txt` | One scoped change, relevant checks, explicit staging and publication |
| `05-finish.txt` | Verify the actual gate and evidence before closing |
| `06-preview-and-recovery.txt` | No-write preview and honest pending-online state |

The label is **`in progress`**, with a space, matching the NF repository.
The description guides selection; it is not a deterministic keyword trigger.
The normal production gate is a merged PR. For this lab, explicitly agree on a
published working-branch handoff. Neither a local commit nor a push is deployment.

After GitHub Copilot CLI has saved the file, run these inside GitHub Copilot CLI:

```text
/skills reload
/skills info issue-lifecycle
```

Confirm the path points to your new file, not another installed copy. Restart
GitHub Copilot CLI if the room version cannot reload. Keep normal tool approvals enabled.
No plugin, MCP server, hook, LSP installation, or unrestricted shell permission
is required for this exercise.

## 3. See your SKILL in action

Try a normal feature request with a **read-only preview**. You do not need to
mention the SKILL:

```text
I want to add the three impact numbers to the homepage using
challenges\01-impact-counters.txt. First, show me how you would
track, build, check, and document this change.
Do not edit files or change GitHub yet.
```

The included `.github\copilot-instructions.md` directs GitHub Copilot CLI to load the SKILL
for feature and bug-fix requests, even when you do not name it. Look for the
actual SKILL load and an issue-first plan with checks and documentation.
If it is skipped, stop before making changes and ask the facilitator to inspect
the setup. Explicit `/issue-lifecycle` is useful for diagnosis, not proof of
automatic selection. Instructions guide the model; they are not a hard policy
that makes missed steps impossible.

Next let GitHub Copilot CLI track the introduction of the SKILL itself:

```text
Start tracking the introduction of this SKILL into my assigned repo.
The draft SKILL.md already exists locally but is not committed.
Record that honestly. This is now an online tracking request,
not the earlier local-file-only authoring task.
For this lab, done means a verified push to my working branch.
Open or reuse one issue, mark it in progress, then stop.
```

This first issue documents the tool you just built. The already-drafted file is
an explicit bootstrap exception, not a claim that an issue preceded it.
For every later feature, start the issue **before** changing code.

Read the issue yourself. Verify the scope and the `in progress` label.

## 4. Make one part yours, before publication

Ask GitHub Copilot CLI to add this **local extension**. Keep the production core intact:

```text
Keep the existing SKILL core unchanged. Append this local extension:

## Local extension

In every completion summary, add a "Next volunteer" line that names one real
file to read next and explains why. Do not invent files or evidence.

Save only the SKILL file. Do not change GitHub, commit, or push.
```

Reload, then repeat a read-only completion preview. Find the new
**Next volunteer** line in the draft; nothing should be posted. This makes your
personalization observable without changing the core's permissions or gates.

The assembled core matches NF's file; your extension is intentionally local.
Do not remove target checks, stop conditions, or honest failure reporting.

## 5. Ask GitHub Copilot CLI to publish and document the result

Review the new file and personalization, then paste this into GitHub Copilot CLI:

```text
Finish introducing the SKILL using the real issue we just opened.
Review the new SKILL.md and its local extension. On a feature branch,
stage only that file and show me the diff. With my normal approvals,
commit with the actual issue number and push the intended branch.

Verify that the remote branch contains the real commit. Then document
what changed, why, the checks, the evidence, follow-ups, and the
Next volunteer line. Post it, close the issue, remove in progress,
and check the final state.

Our agreed lab finish is the verified branch push, not a deployment.
Follow any stricter repository rules. If a step fails or is blocked,
report what remains pending rather than claiming completion.
```

Let GitHub Copilot CLI run the steps; you review its proposed actions and approve the
intended ones. Use the facilitator-provided commit identity. Check the actual
GitHub issue and published change, not only the model's success statement.

If you personalize again after the introduction is complete, track that
published follow-up separately. An unpushed local extension is not a published update.

## Just in: your team has 10 new feature requests

Pick one, or take on all 10. Build them with **GitHub Copilot CLI**, using your
new SKILL in the process. Choose any `.txt` brief and work through your choices
one at a time. Each feature gets its own issue and documentation.
The requesters are real [NF team members](https://www.nuevofoundation.org/about-us).
The requests are written for this lab, not quoted messages or a production backlog.
Beatris requests the impact figures, Mollee the blog, Oliver the curriculum,
and the other briefs introduce more teammates.
There is no need to finish all 10 during the session.
The guide includes a normal feature prompt. You should not need to repeat the
tracking/documentation checklist or type the SKILL's name for every feature.
Each **Open PM brief** link opens the original `.txt` file in a new tab,
so you can keep the lab guide open. It works offline and without JavaScript.

| Brief | Concrete feature |
| --- | --- |
| [01](challenges/01-impact-counters.txt) | Three grounded impact values and their source caveat |
| [02](challenges/02-local-blog.txt) | Blog index and three complete local sample articles |
| [03](challenges/03-team-cartoon-cards.txt) | Sixteen team cards with original local cartoon avatars |
| [04](challenges/04-nine-concept-workshop.txt) | NF workshop explaining all nine concepts, plus a local quiz |
| [05](challenges/05-workshop-finder.txt) | Searchable, filterable five-item practice workshop catalog |
| [06](challenges/06-volunteer-paths.txt) | Three volunteer paths with preparation checklists |
| [07](challenges/07-workshop-request-preview.txt) | Accessible request preview that sends and stores nothing |
| [08](challenges/08-bilingual-introduction.txt) | English/Spanish introduction with correct language semantics |
| [09](challenges/09-project-showcase.txt) | Three illustrative project cards with expandable learning notes |
| [10](challenges/10-program-faq.txt) | Six grounded, keyboard-accessible FAQ entries |

The data is in [challenge-data/content.json](challenge-data/content.json).
The team-feature card uses the supplied Nuvi mascot at
`assets/Nuvi-Robot.svg`, bundled locally and unchanged. It is available as a
team-page placeholder; the original sixteen per-person SVG examples remain.
Read it as coding context; avoid runtime JSON `fetch` under `file://`.
Use plain `.html`, CSS, and optional ordinary JavaScript. No framework, backend,
image service, production deploy, payments, or personal-data collection.
Do not undo earlier completed features. Finish one record before starting another.

## What counts as success?

**Core:** your saved SKILL is discovered from the right path, and a bounded
invocation shows the expected workflow. **Online practice:** its introduction
has a genuine issue and published evidence. **Personalization:** one local rule
produces an observable preview change. **Bonus:** any completed PM feature.

If model services are down, a manually assembled SKILL is still a useful
artifact, but mark runtime invocation **unverified**. Do not call a cached demo
a live run or claim blocked GitHub operations succeeded.

## Three recovery lanes

| Failure | Honest fallback |
| --- | --- |
| SKILL missing or not selected | Exact path/capitalization, save, reload/info, explicit `/issue-lifecycle`; then use the inactive rescue copy |
| GitHub Copilot CLI works but GitHub is unavailable | With approval, continue locally and record `LOCAL ONLY / PENDING ONLINE`, actual checks, and remaining remote steps |
| Model service is unavailable | Manually assemble the bundled parts, walk the checklist, and inspect cached real evidence; runtime remains unverified |

Read [rescue/WALKTHROUGH.md](rescue/WALKTHROUGH.md). Never weaken controls or use
personal room credentials to get around a restriction.

## Two repositories, different jobs

This **starter** is your editable practice canvas and locally grounded brief pack.
The **[supplemental repository](https://github.com/NuevoFoundation/copilot-cli-skills-reference)**
has explanations and examples of all nine concepts to explore on your own time.
It is not a second required lab or nine installations. In the room, use the
organizer's imported copies because managed accounts cannot access these public repos.

After the session, use your own approved account and a disposable repository.
The latest published starter is on this repository's `main` branch. The
organizer's imported copy is a separate snapshot; coordinate its refresh before the session.

**Next week: choose one repeated workflow on your team and make it a SKILL.**

Facilitators: Beatris "Bea" Mendez Gandica and Jeremiah Isaacson, Nuevo Foundation.
