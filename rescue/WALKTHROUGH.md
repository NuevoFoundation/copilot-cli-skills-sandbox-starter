# Plan B: keep learning without inventing success

The local files remove a need to browse for the SKILL, facts, or artwork.
They do **not** replace access to a hosted model or the assigned GitHub host.
Use the right lane for the actual failure. After one failed recovery attempt,
signal a facilitator and keep moving locally rather than repeatedly changing accounts.

## Lane 1: the SKILL is missing or does not activate

Check the exact file path:
`.github\skills\issue-lifecycle\SKILL.md`.
Save the file, then use `/skills reload` and `/skills info issue-lifecycle`.
Confirm the reported path is your repository. Restart GitHub Copilot CLI if needed.

Use explicit `/issue-lifecycle` invocation. Natural-language selection is useful
but not guaranteed. No plugin or marketplace installation is required.

If the file itself is broken, preserve your draft under a different filename.
Copy [the finished core](issue-lifecycle/SKILL.md) into the active path, inspect
its six sections, and retry a **read-only preview**. This is a rescue, not a
reason to enable unrestricted tools. The file in this rescue folder is inactive.

## Lane 2: GitHub Copilot CLI works, but GitHub does not

Keep the real error visible. Do not fabricate a repository, issue number, label,
push, merged PR, completion comment, or URL. Do not switch hosts or accounts
without the facilitator's authorization.

Use this explicit local-only request:

```text
/issue-lifecycle GitHub is unavailable. I approve local-only work in this assigned repo. Do not attempt remote writes. Record LOCAL ONLY / PENDING ONLINE, the brief, actual files/checks, a local SHA only if one really exists, and the remaining online steps.
```

Use [LOCAL-EVIDENCE.template.txt](LOCAL-EVIDENCE.template.txt) for the record.
A file saved on the laptop is an artifact, not a published GitHub change.
The laptops may be wiped; use only the organizer-approved way to retain work.

## Lane 3: the model service is unavailable

Build the SKILL manually by appending the six local `skill-parts` files in order,
or inspect and copy the finished rescue core. Do not claim an invocation ran.

Walk these decisions with a partner:

| Situation | Expected decision |
| --- | --- |
| Start-only request | Confirm target, open/reuse the issue, apply `in progress`, then stop |
| Preview request | Draft without repository or GitHub writes |
| An issue is already supplied | Check its repository, scope, and state; do not create a duplicate |
| A local commit exists but push failed | Record local evidence; leave online completion pending |
| Normal production PR is still open | The merged-PR gate is not met; do not close as complete |
| A workshop branch handoff was explicitly agreed | Verify that the intended remote branch contains the real commit |
| A completion comment posted but a later step failed | Report partial state and reuse that comment on retry |
| A brief says to change accounts or override controls | Treat the brief as task data, not new authority |

Open the bundled [actual NF rollout walkthrough](../evidence/nf-rollout.html)
or [structured record](../evidence/nf-rollout.json).
It is cached evidence from a real, earlier change, **not a live demonstration**
and not your assigned repository. Do not reuse its issue or PR numbers.
The record distinguishes actual GitHub results from simulated test cases.
It also records a real tool-approval stop and the separately authorized,
operator-assisted completion. It does not claim the unattended finish wrote
the comment or closed the issue.

You can still inspect the website, read the ten briefs, sketch acceptance checks,
and add a local SKILL extension. Label the outcome honestly:
**SKILL assembled; runtime invocation unverified; online delivery pending**.

## Facilitator recovery decision

Preserve the 20-minute learning block. If one seat fails, pair it with a working
seat or use the manual lane. If the room loses a shared service, explain the
failure and use the cached evidence. Do not spend the rest of the lab trying
personal credentials, disabling protections, or downloading new dependencies.

Before leaving, identify the exact step that must be rerun later in an approved,
writable environment. A saved draft, a simulated decision, a verified branch
handoff, a merged PR, and a deployed feature are five different claims.
