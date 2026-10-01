# issue-lifecycle SKILL (you build this)

Ask GitHub Copilot CLI to create your SKILL here as a file named `SKILL.md`.
Use the comprehensive prompt in `lab-guide.html`; you do not need to assemble
the file by hand.

Follow the repository `README.md`, section "2. Ask GitHub Copilot CLI to build the SKILL",
or open `lab-guide.html`. GitHub Copilot CLI uses the six local files in `skill-parts/`
to reconstruct the exact NF core. Later, ask it to add your local extension.
After it saves `SKILL.md`, run `/skills reload` and `/skills info issue-lifecycle` inside
GitHub Copilot CLI. Confirm it points to your working repository, not another installed copy.
The completed example in `rescue/issue-lifecycle/` is not loaded automatically.
