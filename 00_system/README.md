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

Stick to this operational framework without variation to establish deep mechanical routine:

### Morning (2 Min)
* Open today's daily note (generated instantly via template).
* Glance at yesterday's "Tomorrow" checklist targets.
* Survey the current-learning dashboard to ground your focus.

### During Practice
* Create concept notes as you encounter new mechanics. Fill them progressively in your own words.
* Drop screenshots used for reference into your design library entries or studies.
* Store heavy working code bases inside your parallel repository, linking the project folder path back to your notes.

### End of Session (90 Sec)
* Complete high-level bullets on active skill tracks in your daily log.
* Log exactly one definitive breakthrough under the realization field. This is the most valuable field for long-term review.

### End of Week, Sunday (30 Min)
* Generate structural weekly review ledger from your template.
* Clear and route all lingering temporary notes or links out of 08_inbox/ into their permanent folders.
* Schedule prospective spaced re-test dates for concepts you want to maintain.

### End of Month (1 Hr)
* Create a monthly summary in 02_weekly/ named YYYY-MM-monthly.md.
* Review mastered concepts and realizations to track broad trajectory and adjust your training roadmap.