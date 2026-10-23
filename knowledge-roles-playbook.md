# Knowledge Roles Playbook

This playbook provides operational guidance for the three knowledge governance roles: Knowledge Lead, Unit Lead, and Organizational Advisor. It translates the rules defined in the [Governance Framework](governance-framework.md) into specific actions, rhythms, and templates.

This is a condensed version of the full client deliverable. It covers the methodology, role model, key workflows, and templates. Detailed onboarding checklists and tool-specific instructions are omitted.

---

## What Knowledge Management Means in Practice

In a high-turnover environment, knowledge management is not about creating documentation after the fact. It is about making sure the things worth saving get saved as a natural part of doing the work.

| Practice | What It Means |
|----------|---------------|
| Capture | When you work on a task, you write down what you found and decided, in the task itself, as you go. Not in a separate document, not in a messaging thread, not after the sprint. |
| Structure | Documentation follows a consistent template so anyone can find and understand it. Same fields, same format, every time. |
| Reuse | Before starting new work, check if someone has already solved this or documented a relevant decision. Search first, create second. |
| Improve | If you find existing documentation that is incomplete or wrong, update it. Everyone is a contributor, not just the original author. |

---

## Methodology: Knowledge-Centered Service (KCS)

All recommendations are grounded in KCS, a methodology developed by the Consortium for Service Innovation for environments where people rotate frequently and knowledge must outlast any individual contributor.

The core principle: capture knowledge as a by-product of doing the work, not as a separate activity after the fact. If documentation only happens at the end of a project, knowledge leaves with the people.

### The Solve Loop: what every team member does daily

| Activity | What It Means |
|----------|---------------|
| Capture | Document what you find and decide in the task itself, as you go. |
| Structure | Follow the task template consistently so others can understand your work. |
| Reuse | Search before creating. Check if someone already documented a solution or decision. |
| Improve | If existing documentation is wrong or incomplete, update it in the moment. |

### The Evolve Loop: what leads do periodically

| Activity | What It Means |
|----------|---------------|
| Content Health | Check that documentation is current, not duplicated, and not stale. Flag what needs updating. Archive what is obsolete. |
| Process Integration | Make sure knowledge capture is built into the workflow, in project templates and sprint checklists, so it is not optional. |
| Performance Assessment | Track simple signals. Can new people find what they need? Is documentation getting completed before tasks close? |
| Leadership Alignment | Unit Leads and the organizational advisor set the example and keep quality standards visible. |

---

## Three Levels of Knowledge

The workspace is organized around three levels. Understanding this structure is the foundation for all knowledge governance work.

| Level | What It Is | Who Owns It |
|-------|-----------|-------------|
| Unit | The primary organizational container (a product line, a department, a function). Each unit has a content page that serves as the long-term knowledge home. | Unit Lead |
| Project | Semester-based or cycle-based project containers where day-to-day work happens. Each project has a task tracker, working agreement, meeting notes, and closure sections. | Knowledge Lead (during the project); Unit Lead (after archival) |
| Task | Individual work items. Every task should be documented well enough that someone new could read it and understand what was done and why. | Assignee; Knowledge Lead checks quality |

---

## Roles at a Glance

| Role | Primary Focus | Operates At | Interacts With |
|------|--------------|-------------|----------------|
| Knowledge Lead | Sprint-level capture; task quality; project closure; ongoing lessons learned | Project level | Team (daily), Team Lead (content gaps), Project Manager (weekly prep), Unit Lead (closure approval) |
| Unit Lead | Unit content page; approving and publishing knowledge; content freshness | Unit level | Knowledge Lead (closure packages), Organizational Advisor (escalation, standards) |
| Organizational Advisor | Cross-unit standards; playbook maintenance; supporting leads | Organizational level | All Unit Leads and Knowledge Leads |

---

## The Knowledge Lead's Weekly Rhythm

### Before the Weekly Team Meeting (20-30 minutes)

- Open the project task board. Review all tasks that moved to Done or Review this sprint.
- For each Done task: does it have a description, an output summary, and relevant links?
- Did any task involve a significant decision? Note it for a Decision Record.
- Are there recurring blockers or patterns worth raising in the meeting?
- If gaps are found: reach out to the assignee and team lead before the meeting.

### After the Sprint (15-30 minutes)

- Note any significant decisions made during the meeting. Add them to a Decision Record.
- Add new lessons to the Lessons Learned section inside the project.
- Update any tasks that had their scope or outcome clarified during the review.

---

## Project Closure: The Critical Knowledge Moment

The Done-to-Archive transition is where a team's accumulated learning either gets preserved for the next team or disappears with the people who built it. This should take one to two weeks, starting during the final sprint, not after the team has disbanded.

The closure process has five parts:

| Part | Purpose | Key Requirements |
|------|---------|-----------------|
| Task-Level Completeness | Ensure all completed tasks have adequate documentation. | All Done tasks have a description, output summary, and relevant links. |
| Decision Records | Capture the most significant decisions made during the project. | Each Decision Record created in the knowledge directory with full metadata. Expect 2-5 per project. |
| Lessons Learned | Extract key learnings into the lessons learned database. | Brief retrospective held with the team. Key lessons extracted using the standard template. |
| Handover Section | Complete the project's post-mortem and handover. | What was built, what is open, what to read first, what to watch out for. |
| Submit for Review | Hand off to the Unit Lead. | All knowledge artifacts linked, all set to In Review status. Nothing moves to Published without Unit Lead approval. |

The Knowledge Lead does not archive the project. Archival is the Unit Lead's responsibility after reviewing and approving all knowledge assets.

### The Unit Lead's Closure Review

When the Knowledge Lead submits the closure package, the Unit Lead reviews four areas:

| Review Area | What to Check |
|-------------|--------------|
| Decision Records | Present for major decisions. Each captures alternatives considered, rationale, and who approved. |
| Lessons Learned | Substantive, not just one-liners. Represent real learnings the next team would benefit from. |
| Promoted Content | Genuinely reusable and accurate. Does not duplicate existing content. Metadata fields are applied. |
| Handover | Useful for the next team. Open items and risks are clearly stated. |

After approval, the Unit Lead promotes content to Published and archives the project. This is the ownership transfer moment: the Knowledge Lead authored the content, but the Unit Lead owns it for the long term.

---

## Decision Record Template

A Decision Record captures why a choice was made, what alternatives were considered, and who approved it. It preserves decision context so future teams do not re-litigate settled questions.

### What Makes a Decision Significant

| Criterion | Example |
|-----------|---------|
| It would be expensive or disruptive to reverse | Choosing a core technology for the application |
| A future team is likely to ask "why was this done this way?" | Dropping support for a specific platform |
| It involved choosing between meaningfully different alternatives | Selecting one library over another with different trade-offs |
| It sets a precedent that affects future work | Establishing an architectural approach or process change |

### Body Structure

| Section | Content |
|---------|---------|
| Decision Statement | One clear sentence: what was decided. If it cannot fit in one sentence, it may be multiple decisions that need separate records. |
| Context | What situation or problem prompted this decision? What constraints existed? |
| Options Considered | Brief description of each alternative evaluated. For each: what it was, main advantage, main drawback. Two to four options is typical. |
| Rationale | Why this option was chosen over the others. Be specific: concrete comparisons are more valuable than general statements. |
| Approved By | Who approved the decision and when. Include the mechanism: team consensus, lead sign-off, executive directive. |
| Consequences and Trade-offs | Known downstream effects. What is accepted or given up. |
| Related Evidence | Links to research, benchmarks, prototypes, external references. |

---

## Lesson Learned Template

A Lesson Learned is any insight from project work that would save a future team time, rework, or confusion, or that would help them repeat a success. It covers more than mistakes: technical discoveries, process improvements, tool findings, collaboration patterns, and pitfalls to avoid.

### Body Structure

| Section | Content |
|---------|---------|
| Context | What were we trying to do? Brief description of the situation. 1-3 sentences. Link to relevant tasks or project. |
| What Happened | What went right or wrong? Be factual. Include specific details (tool versions, team size, timeline). |
| What We Learned | The actual insight. Actionable and specific. "We learned that X" is stronger than "X is important." |
| Recommendation | What should the next team do differently? Write as instructions: "Do X before Y" or "Avoid Z when working with [tool]." |
| Evidence and Links | Links to source tasks, documents, code, meeting notes. |
| Applicability | Who else should know this? Tag other units or topics. |

### Lifecycle

| When | Who | Action | Status |
|------|-----|--------|--------|
| During sprints | Knowledge Lead | Capture rough notes inside the project (not in the database yet). | Not yet in database |
| Project closure | Knowledge Lead | Extract key lessons into the database using the template. | Draft |
| Closure review | Unit Lead | Reviews closure package including lesson entries. | In Review |
| After approval | Unit Lead | Promotes to Published. Lessons appear in unit content views. | Published |
| Monthly health check | Unit Lead | Reviews Last Reviewed dates. Archives superseded lessons. | Published or Archived |

---

## Decision Record vs. Lesson Learned

| Dimension | Decision Record | Lesson Learned |
|-----------|----------------|----------------|
| Core question | What did we decide and why? | What did we learn and what should the next team know? |
| Timing | When a significant choice is made | Ongoing throughout the project; finalized at closure |
| Typical count per project | 2-5 (major decisions only) | 2-5+ (broader range of insights) |
| Long-term value | Prevents re-litigation of settled choices | Prevents repetition of past mistakes |

Decision Records and Lessons Learned often relate to each other. A decision may generate a lesson. The governance framework uses bidirectional relation properties to connect them, creating a traceability chain between decisions and outcomes.

---

*This playbook is a condensed version of a client deliverable produced by [Coreso Collaborative](https://coresocollaborative.com). Client-identifying details have been removed. The full engagement is described in the [case study](README.md).*
