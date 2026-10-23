# Knowledge Governance for a Nonprofit with Semester-Based Teams

When an organization prepares its knowledge base for AI, the work starts well before any model is connected. The AI will only be as reliable as the content it reads: if pages have no lifecycle status, no ownership, and no way to distinguish a current document from an abandoned draft, the AI will surface unreliable answers. This case study documents a consulting engagement that built the governance layer first, designed from the start for both human navigation and machine readability.

## What This Repository Contains

- **This file:** the case study narrative: context, approach, solution, and key design decisions.
- **[Governance Framework](governance-framework.md):** the structural rules: metadata schema, content lifecycle, content types, governance roles, and agent readability design. Condensed from the full client deliverable.
- **[Knowledge Roles Playbook](knowledge-roles-playbook.md):** the operational guide: role definitions, weekly rhythms, project closure workflows, and templates for decision records and lessons learned. Condensed from the full client deliverable.

---

## Client

A Canadian nonprofit working in social innovation, operating fully remote with intern and volunteer teams that turn over on semester funding cycles. The organization runs its operations in Notion, including project management, task tracking, and documentation.

## Context

The organization works in semester cycles. Teams join for a defined period, deliver project work, and hand over to the next group. Each cycle produces documentation, decisions, and project material in the workspace.

The workspace had grown the way active workspaces grow: project by project, shaped by whoever was delivering at the time. It carried structured project workflows and teams that documented their work as they went. What it did not yet have was the layer above individual projects: naming conventions that hold across teams, a content taxonomy, a defined lifecycle for standalone documents, and metadata that records who owns a page and when it was last confirmed as current.

Where the same people stay for years, that layer can remain informal, because people carry the organizing logic themselves. Where teams change every semester, it has to be written down, or each new group rediscovers the workspace from the beginning. The engagement was scoped to build that layer.

## Approach

### Discovery

The assessment drew on three data sources:

- **Exit survey responses** from departing interns and volunteers, covering onboarding experience, tool usage, and improvement suggestions. Navigation was the most frequently raised theme: not that content was missing, but that people were not always able to find content that already existed.
- **Stakeholder interviews** across leadership, technical, and delivery roles. These covered current workflows, role definitions, lifecycle gaps, and operational constraints that survey data alone could not surface.
- **A structural review of the workspace:** organizational units, projects, task templates, content pages, and property schemas. This showed the information architecture as built rather than as described.

### Diagnostic Framework: Four Structural Gaps

Knowledge-Centered Service (KCS) provides a way of grouping how content fails. Applied to the findings, it identified four gaps:

| Gap | What It Means |
|-----|---------------|
| **Discovery** | Content exists but is hard to find. Without a taxonomy, naming conventions, or defined entry points, keyword search is the only route in. |
| **Authority** | Content is found but its status is unclear. Without lifecycle states and named owners, a current document and an abandoned draft look the same. |
| **Freshness** | Content ages without a signal. Without review dates, a page that was accurate six months ago still reads as current. |
| **Transfer** | Knowledge stays with the people who created it. Without a capture step at project close, decision rationale and lessons learned are not carried forward. |

The four gaps reinforce each other. Knowledge that is not captured cannot be kept current; content that is not kept current loses authority; content that cannot be trusted is not worth searching for; and when people stop searching, they document less. Because the cycle is closed, an intervention at any point produces improvement at the others.

### Methodology

All findings and recommendations were grounded in **Knowledge-Centered Service (KCS)**, a methodology developed by the Consortium for Service Innovation for environments where people rotate frequently and knowledge must outlast any individual contributor.

KCS fits this operating model directly: teams that change on a fixed cycle, short funding periods, and a need for content that serves both human navigation and machine readability. Its core principle, capturing knowledge as a by-product of doing the work rather than as a separate activity afterwards, is what makes capture survive a team handover.

## Solution Design

The design treats the knowledge base as a **pipeline** rather than a repository. Content enters as a Draft, moves through review as a quality gate, earns Published status when approved, and is Archived with a documented reason when it is no longer current.

The recommendations were organized around three pillars, sequenced deliberately:

**Structure** (where knowledge lives and how it is organized): a governed knowledge directory with required metadata, a four-stage content lifecycle, eight content types, naming conventions, and standardized information architecture. Structure comes first because people need a system to work in before they can be accountable for it.

**People** (who is responsible for knowledge quality): a three-tier role model with clear ownership at every level. The team-level knowledge lead captures and structures content during projects. The unit-level lead approves content promotion and conducts monthly health checks. The organizational-level advisor maintains standards and resolves cross-unit questions. People comes second because processes require someone responsible for executing them.

**Process** (what they do, when, and how it is verified): a structured project closure workflow, weekly knowledge lead cadence, monthly content health checks, and content promotion procedures. Process comes last because it only works when the infrastructure exists and someone owns it.

### Dual-Audience Design

Every governance element was specified to serve two audiences at once: people navigating the workspace, and AI agents or API-based workflows querying it programmatically. Each metadata property, lifecycle state, and naming convention carries descriptions written for both human readers and machine consumers. This positions the knowledge base for agentic and API-connected workflows without requiring a separate technical layer later.

See the [Governance Framework](governance-framework.md) for the metadata schema and agent readability specifications.

## Deliverables

The engagement produced four interconnected deliverables:

1. **Current-State Assessment:** analysis of all three data sources, structured around the four-gap diagnostic framework, establishing the reasoning behind each recommendation.

2. **Knowledge Management Governance Framework:** metadata schema with required properties, eight content types, four-stage lifecycle with defined progression rules, naming conventions, information architecture standards, governance roles and authority, and success metrics. This is the policy-level document. See [condensed version](governance-framework.md).

3. **Knowledge Roles Playbook:** role-specific operational guidance for knowledge leads, unit leads, and the organizational advisor. Weekly and monthly checklists, the project closure workflow, worked scenarios, a practical KCS introduction, and templates for decision records and lessons learned. Written to be usable by someone in their first week on the job. See [condensed version](knowledge-roles-playbook.md).

4. **90-Day Implementation Plan:** all recommendations mapped to a week-by-week schedule across three phases (Build, Activate, Scale) with role assignments and checkpoints.

A sandbox pilot was built in the client's workspace and reviewed with the executive sponsor across three working sessions, validating the practical fit of the databases, templates, and relational connections before the framework was finalized.

## Key Design Decisions

**Content does not move backward.** Where teams change every semester, allowing content to revert from Published to Draft creates ambiguity about what can be trusted. Significant revisions create a new Draft, and the original is archived with a cross-reference.

**Draft is an entry point, not a quality claim.** The lifecycle only produces value if work is registered while it is still in progress. Draft status carries no expectation of completeness. Its purpose is to make in-progress work visible and findable, with review as the point where quality is assessed.

**A template needs a trigger and an owner.** A template that is available but not assigned tends to stay unused. Every template in this framework is tied to a named role, a trigger event that prompts its use, and a review step.

**Infrastructure before rollout.** Publishing role guidance before the supporting databases and templates exist sets expectations the system cannot yet meet. The implementation plan builds the structure first, activates the roles second, and scales third.

**Archive, never delete.** Where the goal is institutional memory, deleting content removes the record of what was tried and why. Archived content stays searchable and carries a documented reason for archival.

## Results

The engagement delivered a complete, implementation-ready governance system: two companion documents (framework and playbook), structured databases and templates demonstrated in a working pilot, and a sequenced 90-day rollout plan.

The framework was accepted for implementation. The 90-day plan gives the organization a defined path from current state to operational governance, sequenced to match its existing project management workflow.

The engagement received the top client assessment score, and the executive sponsor described the deliverables as business-grounded and ready to implement.

## Methodology and Tools

- Knowledge-Centered Service (KCS)
- Qualitative analysis (stakeholder interviews, exit survey analysis)
- Notion (workspace review, sandbox pilot, template design)
- Information architecture and metadata design

---

*Coreso Collaborative provides knowledge governance consulting for organizations where institutional knowledge must survive team transitions and where AI readiness depends on content that is structured, owned, and trustworthy. Published with the client's permission under the terms of the engagement's non-disclosure agreement. The organization is not named and identifying details have been removed.*
