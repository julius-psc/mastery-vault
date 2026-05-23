# Mastery Vault Operational Guide

This guide documents the rules, naming conventions, and daily workflows required to keep this vault organized and functional.

---

## Part 1: Tag Taxonomy and Rules

Never invent structural tags arbitrarily. New metadata rules must be declared inside 00_system/tags.md first.

### 1. Frontmatter Properties (Metadata Tracking)
These tags must only be applied inside the properties/frontmatter at the top of your notes to control the automated dashboards:
* #status/learning — Active conceptual focus. Tracks on your live dashboard.
* #status/mastered — All criteria passed. Moves note to your personal textbook.
* #status/maintenance — Passed mastery check, routinely monitored for regression.
* #status/stuck — Hard blocker encountered. Flags for critical triage.
* #disc/engineering, #disc/design, #disc/illustration, #disc/motion — Disciplinary categories.

### 2. Inline Content Tags (Transient and Actionable)
Type these directly inside the body of your notes during practice or review:
* #topic/ — Specific technical sub-components (e.g., #topic/typescript, #topic/easing).
* #source/ — External provenance identifiers (e.g., #source/linear, #source/vercel).
* #review/weekly, #review/monthly — Flags for upcoming review sessions.
* #question — Open question requiring research or follow-up.
* #realization — High-value functional breakthrough or insight.

### 3. Core Tag Rules
* Always use the slash hierarchy hierarchy (#status/learning, not #learning) so Obsidian groups them into collapsible trees.
* Structured metadata goes in the frontmatter properties. Transient thoughts (#question, #realization) stay inline in the text body.

---

## Part 2: Uniform Naming System

Enforce this naming pattern strictly to keep files sortable and predictable over multi-year timelines:
* **Daily Logs:** YYYY-MM-DD (e.g., 2026-05-20)
* **Weekly Reviews:** YYYY-[W]WW (e.g., 2026-W21)
* **Core Concepts:** Strict kebab-case formatting (e.g., closures, spring-physics)
* **Design Dissections:** YYYY-MM-DD - product - subject (e.g., 2026-05-20 - linear - command palette)
* **Motion Recreations:** YYYY-MM-DD - product - element
* **Illustration Studies:** YYYY-MM-DD - reference - subject

---

## Part 3: Purpose of the Dashboards

Your three pinned dashboards track your learning state automatically using backend queries:
1. **Learning (current-learning.md):** Shows a real-time list of all active research, current design theory, and open technical hurdles. It pulls any note where status is set to learning.
2. **Mastered (mastered.md):** Acts as your growing personal digital textbook and cumulative index of hard knowledge. Notes automatically move here when status is updated to mastered.
3. **Recent (recent-work.md):** A multi-stream operational ledger reflecting your deep work velocity over the trailing 7 days, compiling recent logs, dissections, and inline realizations.

---

## Part 4: How Code Lives in the System

Code handling is split into two complementary environments to prevent vault bloat while maintaining searchable documentation:

1. **Inline Reference Snaps:** Core algorithmic functions, small definitions, and short execution cases live inside the Obsidian note inside explicitly typed fenced markdown code blocks. This makes your baseline syntax instantly searchable via global search (Cmd + Shift + F).
2. **The Code Repository (mastery-code):** Heavy, working multi-file builds, practice projects, mockups, and application code bases live completely outside the vault inside your parallel Git directory (~/mastery-code).

### Cross-Linking Protocol:
* Inside your external project files, use Obsidian URIs to link to documentation: `obsidian://open?vault=Mastery&file=...`
* Inside your Obsidian concept notes, use file URLs to link directly to local repository folders: `file:///Users/juliuspeschard/mastery-code/...`

---

## Part 5: The Operational Cycle

### 1. Morning — open today's daily log

Open Obsidian. Press `Cmd+P` → type "Daily note" → enter. (Or click the calendar icon if you have Periodic Notes set up properly.)

This auto-creates: `01_daily/2026-05-23.md` with your daily template pre-filled.

Glance at yesterday's "Tomorrow" field. That's where you start.

### 2. During a learning session — create concept notes as you encounter them

When you start learning a new concept (e.g. closures), create the concept note:

- **Engineering concept** → new file in `03_engineering/concepts/closures.md` (Templater auto-applies the engineering concept template)
- **Design concept** → new file in `04_design/concepts/easing-curves.md`
- **Motion recreation** → new file in `06_motion/recreations/2026-05-23-linear-hover-state.md`
- **Illustration study** → new file in `05_illustration/studies/2026-05-23-blender-donut.md`
- **Design dissection (daily exposure)** → new file in `04_design/library/2026-05-23-linear-command-palette.md`

You fill these progressively as you learn. They're your personal textbook.

### 3. During the session — drop screenshots inline

When you need to capture a screenshot, just paste it directly into the note you're working in (`Cmd+V`). Obsidian auto-saves it to `_attachments/` next to that note.

For code: paste it directly in the concept note inside fenced code blocks with the language tagged (` ```ts `, ` ```rust `, etc.). For substantial code (anything more than ~30 lines), put it in your parallel `mastery-code` repo and link to the file path from the concept note.

### 4. Anything you don't have time to file properly → inbox

If something interesting crosses your desk mid-session — a link, a half-thought, a screenshot you'll process later — drop it in `08_inbox/`. Don't decide where it goes in the moment. Triage on Sunday.

### 5. End of session (90 seconds) — fill the daily log

Open today's `01_daily/2026-05-23.md`. Fill the template:

- **Engineering**: focus + 1 bullet on what you built/practiced + 1 bullet on what you got stuck on
- **Design**: focus + link to today's library dissection + what you practiced
- **Illustration**: focus + what you practiced
- **Realization**: the one thing that clicked today (most important field)
- **Tomorrow**: 1 bullet for what you'll start with tomorrow

Save. Done. 90 seconds.

Git plugin auto-commits within 30 min. Nothing for you to do.

---

### Sunday only — weekly review (30 min)

`Cmd+P` → "Weekly note" → fills `02_weekly/2026-W21.md` from template.

- List concepts that hit `status: mastered` this week (update frontmatter on those concept notes)
- List concepts still shaky → schedule next week's re-tests
- Be honest about where you wasted time
- Triage your `08_inbox/` — move each item to the right folder
- Re-do 2-3 exercises from earlier weeks without notes (spaced repetition)

### End of Month (1 Hr)
* Create a monthly summary in 02_weekly/ named YYYY-MM-monthly.md.
* Review mastered concepts and realizations to track broad trajectory and adjust your training roadmap.