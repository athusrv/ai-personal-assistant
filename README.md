# Sierra Personal AI Assistant

**v0.1.0** — a portable personal development assistant for Sierra teammates. Each person chooses their own **growing edge**, connects their own work context, and receives practical suggestions for alignment, commitments, learning and sync preparation.

This is an instruction-based Agent Skill with reusable templates. It includes no server, shared employee database, connector credentials or background scheduler. The host assistant supplies document reading, integrations, private storage, scheduling and notifications. Installing the skill alone does not activate any of them.

## Start by talking to your assistant

1. Install the **whole** [`skills/sierra-personal-assistant`](skills/sierra-personal-assistant/SKILL.md) folder, including its references and assets, in a compatible agent. See [setup and compatibility](docs/setup.md).
2. Say: **“Use $sierra-personal-assistant to help me set up my growing edge. I can describe it or share written feedback.”**
3. Review the proposed interpretation, observable goal and boundaries. Feedback is optional; one document is not a definitive assessment.
4. Choose a private storage location outside this checkout and all other repositories. The assistant creates a profile after agreement. Without persistent storage, use a private conversation and save a copy yourself.
5. Select relevant Slack, Fellow and/or Calendar sources. The assistant verifies each available connector and limits its queries to your approved scope.
6. The assistant **recommends** morning, end-of-day and weekly routines tailored to your edge. Choose which to enable, the days, local time, time zone and private delivery destination. It configures supported scheduling tools and reports the verified result, or explains the fallback.

No programming or manual profile editing is needed when your agent can read documents and save private files. You can decline sources, storage or automation and still use the coaching workflow.

## What it helps with

- **Individual onboarding:** interpret written feedback, reviews or documents; distinguish evidence from hypotheses; confirm a focus before saving it.
- **Alignment & Communication:** surface decisions that need input before execution, draft updates, and close open commitments.
- **Delegation & Empowerment:** identify opportunities to transfer ownership and support autonomy.
- **Strategic Thinking:** connect decisions to outcomes, assumptions and trade-offs.
- **Sync preparation:** gather relevant decisions, open questions, commitments and a concise agenda with source references.
- **Learning and weekly reflection:** compare observable behavior with the chosen goal and suggest one small experiment.
- **Proactive check-ins:** recommend and help configure recurring routines, with quiet behavior when nothing actionable changes.

Examples are fictional. The skill adapts to other growing edges without changing shared instructions.

## Privacy and action boundaries

Each installation belongs to one person. Real profiles, feedback, transcripts, source links and routine histories stay in private user-controlled storage. They are never committed, uploaded to issues or included in team reports. A private repository is still shared with its collaborators; it is not personal storage.

The assistant can deliver approved reminders to the individual. Messages to colleagues, shared-document edits and calendar changes require explicit approval of the concrete action. It does not score employees, compare people or report development information to management. Read [privacy and retention](docs/privacy.md) before supplying work material.

## Package contents

- [`SKILL.md`](skills/sierra-personal-assistant/SKILL.md): entrypoint and behavior.
- [`references/`](skills/sierra-personal-assistant/references/onboarding.md): onboarding, source handling, alignment, syncs, learning and automation procedures.
- [`profile.template.md`](skills/sierra-personal-assistant/assets/profile.template.md): blank private-profile template.
- [`automations.template.json`](skills/sierra-personal-assistant/assets/automations.template.json): scheduler-neutral routine proposals; all disabled.
- [`examples/`](examples/onboarding.md): fictional feedback, profiles, prompts and expected outputs.
- [`setup.md`](docs/setup.md): installation, connectors, automation activation and verification.

## Updating and sharing

Update only the shared skill folder; retain private profiles and runtime state separately. Reconfirm changes to the growing edge or automation scope. Keep this repository private unless its owner explicitly changes that decision. Check destination organization policies before forking or transferring; neither operation includes private runtime data.

The package follows the [Agent Skills structure](https://agentskills.io/specification). For host-specific behavior see [official skill documentation](https://learn.chatgpt.com/docs/build-skills) and [scheduled task documentation](https://learn.chatgpt.com/docs/automations?surface=app). Capability and availability checks happen in the target account; this package does not guarantee a particular platform integration.
