# Setup and compatibility

## Install the skill

Keep the folder name `sierra-personal-assistant` and copy its complete contents, not just `SKILL.md`.

- **Codex:** open this project and ask the built-in skill installer to install `skills/sierra-personal-assistant` as a personal skill, or copy that folder to `~/.agents/skills/sierra-personal-assistant`. For project-scoped discovery, use `.agents/skills/sierra-personal-assistant` in the intended working project. Avoid duplicate installations with the same name. [Official discovery locations](https://learn.chatgpt.com/docs/build-skills).
- **Other Agent Skills hosts:** install or import the complete folder using that host's documented skill mechanism. Use its file-upload and connector features where available. Standard skill packaging does not guarantee host support for scheduling or persistence.
- **Instruction-only fallback (including hosts without skill imports):** attach `SKILL.md` and the relevant references/assets in a private conversation, or paste their contents as instructions. Do not claim they were installed as a native skill. Upload the profile separately only to a destination approved for personal work data. Reattach context if the host cannot retain it.

Start with: “Use $sierra-personal-assistant to configure my personal assistant.” If the host uses another invocation syntax, select the installed skill there. No API keys are needed by this package; a host or connector may have its own access requirements.

## Establish private storage

The agent should help create the profile conversationally. A user-chosen directory such as `~/.sierra-personal-assistant/` is a suggested location, **provided it is outside every repository and shared/synced team folder**. A private filesystem path does not itself provide encryption or an access policy. Use operating-system access restrictions and company-approved storage. Do not persist raw feedback by default.

Verify the selected path, write permission and ability to reread the profile. If not permitted, keep a session-only profile and offer a private copy. The shared example and template are never edited into real profiles. `profile.md`, `private/` and other patterns are ignored as a second layer; `.gitignore` is not an access-control mechanism.

## Connect only relevant sources

1. In the target assistant, inspect available connectors for Slack, Fellow and Calendar. Use the assistant's supported connection flow; never put tokens in this repository or a prompt.
2. Agree on the specific account/workspace, channels, meeting series/calendar, time range and exclusions. DMs are excluded unless explicitly selected. You can use one source, several, or none.
3. Make a small read-only query per selected source. Report successful scopes and failures separately. Metadata-only calendar access cannot establish what was discussed in a meeting.
4. Confirm that the proposed scheduled runtime has the same required access. A connector that works interactively may be unavailable in background runs.

This package does not ship MCP server URLs or create accounts. Use approved existing connectors. Do not grant broader permissions just to make a check-in work. Missing integrations can be replaced by user-supplied excerpts or a manual check-in.

## Configure proactive routines

The skill must offer routines during onboarding. It must not activate them without the person's choice. See the [automation procedure](../skills/sierra-personal-assistant/references/automations.md) and [example prompts](../examples/automation-prompts.md).

The [JSON template](../skills/sierra-personal-assistant/assets/automations.template.json) is a **scheduler-neutral planning format**, not a platform API payload or an automatically imported file. Its routines start disabled. The agent copies it to private `automations.local.json`, fills the agreed settings and maps them to the actual scheduler tool schema.

Before activation confirm the IANA time zone, working days, local time, private delivery destination, source scope and notification behavior. Resolve the profile path explicitly in that runtime. Ignored files may be absent in an isolated worktree, and web tasks cannot read a local profile by path. Do not copy a personal profile into Git to solve this.

For local scheduled tasks, verify the app/computer availability requirements. For hosted tasks, use a company-approved private context mechanism or fall back to a non-sensitive reminder to start an interactive session. Keep only minimal necessary instructions in the task prompt; task metadata may be visible to others depending on the host. See [official scheduled task documentation](https://learn.chatgpt.com/docs/automations?surface=app).

After creation, reread each task's ID, status, recurrence, time zone and next run if exposed. Perform an authorized preview or test where available. Creation and successful notification delivery are separate facts. If delivery cannot be tested, say so. Provide the scheduler's pause/edit instructions and verify changes after applying them. This repository publication does not activate any personal routines.

## Check the installation

- Start onboarding from a goal and from a fictional feedback excerpt.
- Verify that the person confirms the interpretation before persistence.
- Verify the private profile is outside the checkout and survives a skill update.
- Simulate an unavailable connector or missing scheduler: the agent must report the limitation and offer a fallback.
- Verify that an update to a colleague remains a draft until explicitly approved.
- Confirm scheduling and delivery independently; do not mistake a JSON template for an active task.

These are manual acceptance scenarios, not claims that every host has been tested.
