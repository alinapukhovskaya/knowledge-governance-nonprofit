# Knowledge Management Governance Framework

This framework defines how an organization creates, organizes, maintains, and retires knowledge content in its workspace. It provides the structural rules and standards that make knowledge findable, trustworthy, and reusable across rotating teams, and machine-readable for AI agents and API-based workflows.

This is a condensed version of the full client deliverable, showing the methodology and design patterns. Tool-specific implementation details (database configurations, template deployment) are omitted.

---

## Guiding Principles

These principles are decision filters: when a new situation arises that is not covered by a specific rule, apply these.

*Grounded in Knowledge-Centered Service (KCS), a methodology for high-turnover environments where knowledge must outlast any individual contributor.*

| Principle | What It Means in Practice |
|-----------|---------------------------|
| Capture during the work, not after it | Documentation happens inside tasks and projects as part of daily work. There is no separate "documentation phase." |
| Every page has an owner and a status | No page in the knowledge directory exists without a named owner and a lifecycle status. If you cannot identify who maintains a page, escalate. |
| Search first, create second | Before creating new content, search for existing pages on the same topic. If found, update the existing page. Duplicate content is treated as a governance issue, not a content issue. |
| If it is not findable, it does not exist | Content without metadata, without a home in the knowledge directory, or buried inside closed projects with no outward link is effectively invisible. |
| Lightweight over comprehensive | A short, accurate, well-tagged page is more valuable than a long, detailed page with no metadata and no owner. Governance adds a few fields to a page, not hours of work. |
| Machine-readable by default | Structured metadata (status, content type, owner, unit, last reviewed) serves both human navigation and AI agent queries. Every governance rule is designed to support both audiences. |

---

## Governance Roles

Knowledge governance operates through three roles distributed across organizational levels.

| Role | Level | Governance Authority |
|------|-------|---------------------|
| Knowledge Lead | Project / Team | Sets Draft status on new content. Assigns Owner field. Populates metadata on all pages created during a project. Submits content for promotion to Published. Authors lessons learned and decision records. |
| Unit Lead | Unit / Department | Approves content promotion from In Review to Published. Owns the unit content page. Archives superseded content. Conducts monthly content health checks. Curates onboarding pages. |
| Organizational Advisor | Organization | Sets and maintains metadata standards, naming conventions, and template structures. Resolves cross-unit governance conflicts. Updates the framework and playbook. |

---

## Content Types

Every page registered in the knowledge directory is assigned exactly one content type. Content types enable filtered views, role-based discovery, and agent-based queries.

| Content Type | Purpose |
|-------------|---------|
| Decision Record | Captures why a choice was made, what alternatives were considered, and who approved it. Preserves decision context for future teams. |
| Lesson Learned | Documents what worked, what did not, and what the next team should do differently. |
| Process | Step-by-step instructions for a repeatable activity. Written so someone unfamiliar with the context can follow it. |
| Research | Findings from investigation, competitive analysis, technical exploration, or user research. Includes sources and methodology. |
| Reference | Stable factual content that does not change frequently. Technical specs, architecture diagrams, glossaries. |
| Guide | Explanatory content that teaches a concept, tool, or practice. Written for learning, not step-by-step execution. |
| Report | Periodic or one-time summaries of progress, findings, or outcomes. Time-bound. |
| Roadmap | Forward-looking plan with milestones, priorities, and timelines. Always has an Owner and a review date. |

---

## Knowledge Lifecycle

All knowledge content follows a four-stage lifecycle. Each stage has a clear definition, a responsible role for the transition, and a specific meaning for anyone reading or querying the content.

| Status | Definition | Who Transitions | Reader Signal |
|--------|-----------|----------------|---------------|
| Draft | Content is being written or is incomplete. Not yet reviewed. | Author creates content in Draft. | Do not rely on this for decisions. It may be incomplete or inaccurate. |
| In Review | Content is complete and submitted for review. | Knowledge Lead moves Draft to In Review and submits to Unit Lead. | Pending approval. Treat as provisional. |
| Published | Reviewed, approved, and the current authoritative version. | Unit Lead approves and moves In Review to Published. | Safe to rely on. This is the canonical version. |
| Archived | Superseded, outdated, or no longer relevant. Retained for historical traceability. | Unit Lead or Organizational Advisor. | Historical reference only. Check if a replacement link points to a newer version. |

### Lifecycle Rules

- **No backward transitions.** Content does not move from Published back to Draft. If Published content needs significant revision, create a new Draft page and archive the original with a link to the replacement.
- **No deletion.** Content is archived, never deleted. Archived pages remain searchable for historical context.
- **Status is required at creation.** Every new page starts as Draft. Pages without a status are non-compliant.
- **Only Unit Lead publishes.** The transition from In Review to Published requires Unit Lead approval. This is the quality gate.
- **Freshness trigger at 90 days.** Any Published page where Last Reviewed is older than 90 days is flagged during the monthly content health check. The page is not automatically downgraded, but it must be reviewed and the date updated, or the page archived.

---

## Metadata Schema

Metadata is what makes the difference between content that can be found and trusted and content that gets ignored. These fields also make the knowledge base machine-readable for AI agents and API-connected workflows.

### Knowledge Directory: Required Properties

| Property | Type | Values / Format | Set By |
|----------|------|-----------------|--------|
| Title | Title | [Unit] - [Type] - [Description] | Author at creation |
| Status | Select | Draft, In Review, Published, Archived | Author > Knowledge Lead > Unit Lead |
| Owner | Person | Single person accountable now | Knowledge Lead at creation; Unit Lead after promotion |
| Content Type | Select | Decision Record, Lesson Learned, Process, Research, Reference, Guide, Report, Roadmap | Knowledge Lead at creation |
| Unit(s) | Relation | Multi-select relation to organizational units | Knowledge Lead at creation |
| Last Reviewed | Date | Manual entry, distinct from auto-generated Last Edited | Knowledge Lead weekly; Unit Lead monthly |

### Knowledge Directory: Optional Properties

| Property | Type | Purpose |
|----------|------|---------|
| Superseded By | Relation to self | If Archived, points to the replacement page. Prevents dead-end navigation. |
| Source Project | Relation | Links knowledge page to the project where it originated. Full traceability from work to knowledge. |
| Review Cycle | Select (Monthly, Quarterly, Annually, Ad Hoc) | Drives the monthly health check schedule. Used with Last Reviewed to calculate next review. |
| Summary (AI) | Text (1-2 sentences) | Agent-optimized summary for search result snippets. |
| Onboarding Essential | Checkbox | Flags pages for "start here" views. Curated by Unit Lead. |

### Lessons Learned Directory: Required Properties

| Property | Type | Values / Format | Set By |
|----------|------|-----------------|--------|
| Title | Title | [Category]: [Concise summary] | Knowledge Lead |
| Status | Select | Draft, In Review, Published, Archived | Knowledge Lead > Unit Lead |
| Category | Select | Software, Hardware, Process, Team and Collaboration, Tools and Infrastructure, External, Other | Knowledge Lead |
| Unit | Select | Organizational unit | Knowledge Lead |
| Source Project | Relation | Links to originating project | Knowledge Lead |
| Impact | Select | High (significant time/rework), Medium (caused friction), Low (nice to know) | Knowledge Lead |
| Owner | Person | Unit Lead (as per ownership model) | Knowledge Lead at creation |
| Last Reviewed | Date | Date of last review or creation | Unit Lead (monthly check) |
| Follow-Up Task | Relation | If the lesson requires action, links to the task. Empty means informational only. | Knowledge Lead |
| Related Decisions | Relation (bidirectional) | Links this lesson to the decision records it emerged from or informed. | Auto (bidirectional) or Knowledge Lead |

---

## Agent Readability

The metadata schema is designed with AI agent use in mind. The following conventions allow agents or API connectors to query the knowledge base effectively.

| Condition | Agent Behavior |
|-----------|---------------|
| Status = Published | Treat as authoritative. Default filter for search queries. |
| Status = Draft | Exclude from default results unless the query explicitly asks for drafts. |
| Status = Archived | Historical reference only. Include only if the query asks for historical context. |
| Owner field | The authority contact for questions about the content. |
| Content Type | Match to user intent. "Why did we decide X?" maps to Decision Record. "How do we do X?" maps to Process or Guide. |
| Last Reviewed older than 90 days + Status = Published | Flag as potentially stale. |
| Superseded By populated | Always redirect to the linked page. |

### Property Descriptions: Dual-Audience Design

Every metadata property carries two descriptions: one for people navigating the workspace, and one for AI agents or API connectors querying programmatically. Examples:

**Status (for people):** Shows where this page is in the review process. Draft means work in progress, do not rely on it. Published means approved and reliable. Archived means superseded or outdated, kept for history.

**Status (for agents):** Default filter: Status = Published. Exclude Draft from search results unless the user explicitly asks for drafts. Archived is historical only, include only if the query requests history. If Superseded By is populated, redirect to the linked page.

**Content Type (for people):** What kind of document this is. Use it to filter views: Decision Record, Process, Guide, Report, and so on.

**Content Type (for agents):** Match to user intent. "Why did we decide X?" maps to Decision Record. "How do we do X?" maps to Process or Guide. "What did the team learn?" maps to Lesson Learned. Use as a primary filter alongside Unit.

**Last Reviewed (for people):** The date someone last deliberately checked that this page is still accurate. Different from the automatic Last Edited timestamp. If this date is more than 90 days old, the content may be stale.

**Last Reviewed (for agents):** If older than 90 days and Status = Published, flag as potentially stale in results. Do not treat as unreliable; flag for human review.

This dual-description pattern positions the knowledge base for AI readiness without requiring a separate technical layer. The same governance system that helps people find and trust content also enables agents to query it reliably.

---

## Key Policies (Summary)

| Policy | Rule |
|--------|------|
| Ownership | Every governed page must have an Owner. When an Owner departs, the Unit Lead reassigns within one week. Assign by role where possible so ownership transfers when people rotate. |
| No duplication | Search before creating. One canonical source per topic. If two pages cover the same topic, the Unit Lead decides which to keep. The other is archived with a replacement link. |
| Archival | Archive, never delete. Archived pages must indicate why. When replacing content, the archived page must link to the replacement. |
| Naming | Knowledge Directory pages follow [Unit] - [Content Type] - [Description]. Decision Records use DR: [Short phrase]. Lessons use [Category]: [Summary]. |
| Quality | Metadata complete. Self-contained (a reader unfamiliar with the project context can understand the page). Sources cited. Actionable. |
| Communication | Publish, then announce. When content is promoted to Published, the team posts a brief message in the relevant channel with a link. |

---

## Governance Metrics

These metrics require no external tools. They can be tracked directly from the knowledge directory using built-in database filters.

| Metric | How to Measure | Target |
|--------|---------------|--------|
| Metadata Completeness | Pages where required fields are empty | 0 pages with blank required fields |
| Content Freshness | Published pages where Last Reviewed is older than 90 days | 0 stale Published pages |
| Knowledge Extraction Rate | Knowledge pages created per completed project | At least 1 knowledge page per closed project |
| Lessons Learned Volume | Published lessons per cycle | Growth over previous cycle |
| Ownership Coverage | Pages where Owner is empty | 0 orphan pages |

---

*This framework is a condensed version of a client deliverable produced by [Coreso Collaborative](https://coresocollaborative.com). Client-identifying details have been removed. The full engagement is described in the [case study](README.md).*
