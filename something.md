something.md

1. Objective
Create a developer enablement program that uses reusable prompts in Windsurf and Claude Code to:

Reduce time-to-onboard for new engineers on common tasks and stacks.

Increase speed and quality of day‑to‑day development work (coding, debugging, refactoring, documentation).

Standardize “how we use AI” so developers get consistent, high‑quality outcomes instead of ad‑hoc prompting.
​

2. Scope
Tools in scope: Windsurf (AI IDE) and Claude Code / Claude in editor.
​

Audiences:

New hires and internal transfers.

Existing engineers who don’t yet use AI effectively.

Tech leads and staff engineers who create advanced “power prompts”.

Activities covered:

Project bootstrapping and scaffolding.

Code generation, refactoring, and test creation.

Debugging and incident triage.

Documentation and design-support prompts.
​

3. Workstreams
A. Prompt Library Design
Create a versioned prompt catalog grouped by use case:

“Start a new service/app” (by tech stack).

“Refactor this file/module safely.”

“Generate tests for X (unit/integration).”

“Debug this failing test/log/error.”

“Summarize and document this module/PR.”
​

For each prompt, define:

Intent, required inputs (e.g., repo context, files, logs), and expected output format.

Do/Don’t guidance (e.g., “Don’t invent APIs; infer from this directory only.”).
​

B. Integration into Developer Workflow
Package prompts as:

Snippets/macros in Windsurf and editor commands in Claude Code.

Template files or “starter tasks” referenced in onboarding playbooks and runbooks.
​

Embed the library into:

Onboarding guides, internal docs, and starter repos.

PR templates (e.g., “Optionally run the ‘Review this diff for risks’ prompt”).
​

C. Onboarding & Training
Create a short “AI dev ramp‑up” module (60–90 minutes):

Why AI‑assisted development, common pitfalls, and expectations.

Hands‑on exercises using a curated set of prompts in Windsurf and Claude Code.
​

Provide “office hours” or champions in each team to gather feedback and refine prompts.
​

D. Feedback & Continuous Improvement
Add feedback hooks to each prompt (thumbs up/down, short form, or Slack thread link).

Run monthly reviews to:

Deprecate low‑value prompts.

Promote high‑impact prompts to “recommended” status.

Capture new patterns from advanced users.
​

4. Measurable Impact & Metrics
Combine outcome metrics (business/engineering impact) with experience metrics (how developers feel), as recommended in modern DX and developer productivity research.
​

A. Onboarding & Time‑to‑Effectiveness
Goal: Show that reusable prompts reduce new‑developer ramp time.

Time to first meaningful PR merged

Definition: median days from start date to first PR above agreed LOC/complexity threshold.

Target: X% reduction vs. previous cohorts (e.g., 20–30%).
​

Time to independent delivery

Definition: median days to first story completed without pairing or heavy code review rework.

Measurement: survey manager and new hire at day 30/60.
​

Onboarding friction score

Short survey after 30 days: “It was easy to get productive in this codebase” (Likert scale).

Target: increase average score by Y points after rollout.
​

B. Developer Productivity & Flow
Goal: Show that prompts improve flow and reduce time lost to repetitive or boilerplate tasks.

Time lost to environment/process friction

Self‑reported weekly: “How many hours did you lose to tooling/process issues?”

Target: decrease average reported “time lost” per dev by X%.
​

AI‑assisted completion rate

% of PRs where authors indicate they used Windsurf/Claude prompts for creation/refactor/test.

Track by PR checklist or tag in description.
​

Lead time for common tasks

Measure end‑to‑end time for: new endpoint, bug fix, test creation in a target repo.

Compare baseline vs. after prompt library adoption; aim for measurable reduction (e.g., 20%).
​

C. Code Quality & Reliability
Goal: Show that AI prompts do not degrade quality and ideally improve it.

Defect rate per change

Post‑release bugs per 100 merged PRs in target services.

Compare before and after rollout; expect stable or improving trend.
​

Code review rework

Average number of review cycles or “requested changes” comments per PR.

Target: reduction in basic issues (style, missing tests, simple bugs) due to better prompts.
​

D. Developer Experience & Satisfaction
Goal: Demonstrate better DX and satisfaction from structured AI use.

DX satisfaction score

Quarterly survey items, e.g.:

“Our dev tools make it easy to get work done.”

“AI tools and prompts help me be more productive.”

Track changes over time; improving DX is correlated with productivity and retention.
​

Perceived productivity and learning

Survey: “Compared to 3 months ago, I feel more productive / I’m learning faster.”

Qualitative comments used to refine prompts and training content.
​

E. Adoption & Engagement
Goal: Ensure prompts are actually used and improved.

Prompt usage analytics

For each prompt: weekly/monthly usage counts, unique users, and teams.

Identify “top 10” prompts and gaps where usage is low but value should be high.
​

Contribution rate to prompt library

Number of contributors and contributions per quarter.

Target: growth over time, indicating community ownership instead of central bottleneck.
​

5. Execution Plan & Timeline
You can adjust the cadence to your organization’s size and urgency.

Month 0–1: Discovery and design

Interview developers to identify high‑friction tasks.

Draft initial prompt sets for Windsurf and Claude Code for 3–5 core workflows.
​

Month 2: Pilot

Roll out to 1–2 squads.

Instrument the metrics above with clear “before” baseline.
​

Month 3–4: Iterate

Refine prompts based on feedback and success/failure cases.

Improve onboarding content and training.
​

Month 5+: Scale

Expand to more teams; integrate prompts into all new onboarding flows.

Review metrics quarterly; adjust targets and investment accordingly.
​

If you share your current onboarding steps and tech stacks, a more tailored prompt catalog and metric targets can be drafted in your format (e.g., Confluence template, Notion doc, or internal RFC).
