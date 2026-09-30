# Build a GitHub issue lifecycle skill (GitHub Universe 2026 Sandbox)

Welcome. In this session you will build one small, complete GitHub Copilot CLI skill and run it end to end. By the time you leave, a skill will feel like what it actually is: a Markdown file with a trigger and a set of instructions.

This repository is a tiny website with one deliberate change waiting to be made. You will not make that change by hand. You will teach Copilot CLI to wrap a tracked GitHub issue around it: open the issue, mark it in progress, and close it with a short writeup that references your commit. That is the Nuevo Foundation house rule: every change gets a tracked issue, no exceptions, and a skill does it for us.

## What you will build (about 20 minutes)

A skill named `issue-lifecycle` that drives the full loop for a unit of work:

1. Open a GitHub issue that describes the work.
2. Mark it in progress.
3. Close it with a writeup that references the commit that did the work.

Then you will run it against the change in this repo, and personalize it with one tweak of your own.

## The room machine

The machine in front of you already has everything you need:

- GitHub Copilot CLI (with Copilot model access for your seat)
- GitHub CLI (`gh`)
- Node.js 22 or later, `git`, and VS Code

You do not need to install anything. You only need to sign in.

## Step 0: Sign in (about 2 minutes)

The laptops are wiped after every session, so nothing is signed in yet. Two quick sign-ins:

```bash
# 1. Authenticate the GitHub CLI (choose GitHub.com, then HTTPS, then a browser or token)
gh auth login

# 2. Start Copilot CLI
copilot

# 3. Inside Copilot CLI, authenticate Copilot
/login
```

Confirm you are ready:

```bash
gh auth status
```

You should see that you are logged in and that this repo is yours to open and close issues in.

## Step 1: Find the change you will wrap an issue around

Open `styles.css`. Near the top you will see the accent color:

```css
--accent: #9aa0a6;
```

That placeholder gray drives the primary button, the hero underline, and the impact cards. The task is to bring it in line with Nuevo Foundation's brand: change it to the yellow already in our logo, `#FCC600`. Do not change it yet. First you will build the skill, then let the skill open an issue, then make the change, then let the skill close the issue.

If you want to see the page, open `index.html` in the browser or use the VS Code preview.

## Step 2: How a skill works (anatomy)

A skill is a single file named `SKILL.md` inside its own folder under `.github/skills/`. It has two parts:

- YAML frontmatter with a `name` and a `description`. The `description` is the trigger: it tells Copilot what the skill does and when to use it.
- A Markdown body with the instructions Copilot should follow when the skill fires.

That is the whole idea. A folder, a `SKILL.md`, a trigger, and instructions.

Your skill folder already exists at `.github/skills/issue-lifecycle/`. You will create the `SKILL.md` inside it. Copilot loads a skill only from a file named exactly `SKILL.md`.

## Step 3: Build your skill

Create the file `.github/skills/issue-lifecycle/SKILL.md`. Start with this frontmatter:

```markdown
---
name: issue-lifecycle
description: Manage the full lifecycle of a GitHub issue for a unit of work. Use this whenever you start, work on, or finish a change, so every change is tracked. It opens an issue, marks it in progress, and closes it with a writeup that references the commit.
allowed-tools: shell
---
```

A note on `allowed-tools: shell`: this pre-approves shell commands so Copilot can run `gh` without asking each time. Only pre-approve `shell` in a skill you wrote and trust, which is exactly the case here.

Now write the body. It should instruct Copilot to do three things, in order:

1. Open the issue. Run `gh issue create` with a clear title and a body that describes the work. Capture the new issue number.
2. Mark it in progress. Signal that work has started, for example by adding a comment, applying an `in-progress` label, or assigning the issue with `--assignee @me`.
3. Close it with a writeup. After the change is committed, run `gh issue close` on that issue number with a closing comment that summarizes what changed and references the commit that did it.

Write these as plain instructions in your own words. When your `SKILL.md` is saved, run `/skills` inside Copilot CLI to confirm it loaded.

## Step 4: Run the open, work, close loop

Now use it, all from plain English inside Copilot CLI.

1. Open. Tell Copilot what you are about to do:

   > Start the work to change the site accent color to the Nuevo brand yellow.

   Your skill should fire and open a GitHub issue, then mark it in progress.

2. Work. Make the one change in `styles.css`:

   ```css
   --accent: #FCC600;
   ```

   Commit it, referencing the issue number your skill created:

   ```bash
   git commit -am "Change accent color to Nuevo brand yellow (#<issue-number>)"
   ```

3. Close. Tell Copilot the work is done:

   > The change is committed. Close the issue.

   Your skill should close the issue with a writeup that references your commit.

Open the issue on GitHub. You should see it opened, marked in progress, and closed with a clean summary. That is the whole lifecycle, driven from natural language.

## Step 5: Make it yours

Pick one tweak and add it to your skill. This is the part you take back to work:

- Label taxonomy: have the skill apply a consistent set of labels (for example `type:chore` and `area:ui`).
- Closing-comment template: make the writeup follow a house format (what changed, why, and the commit).
- `--assignee @me`: auto-assign every issue to yourself when it opens.
- Retroactive-issue mode: open an issue for a change you already made, then close it referencing the existing commit.
- `Closes #<id>` in a PR: open a pull request whose description auto-closes the issue when it merges.

## Stuck?

Flag a facilitator (Bea or Jeremiah) and we will unblock you. A finished version of the skill is on hand if you want to compare, but try to build yours first: the point is the muscle memory, not the finished file.

## After the session

Take home the reference repo: `NuevoFoundation/copilot-cli-skills-reference` (link shared in the room). It has a working example of every Copilot CLI extension layer (instructions, prompts, agents, skills, hooks, MCP, and plugins), each with a short README on when to reach for it.

One call to action: pick one repeated workflow on your team next week and make it a skill.

## Facilitators

- Beatris "Bea" Mendez Gandica, CEO and Founder, Nuevo Foundation (GitHub: @beagandica)
- Jeremiah Isaacson, CTO, Nuevo Foundation (GitHub: @jeremiahjordanisaacson)
