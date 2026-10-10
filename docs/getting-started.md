# Getting Started

This guide explains how to turn the master template into a project-specific Product Requirements Document (PRD). The repository is documentation-only: you do not need to install React, FastAPI, PostgreSQL, or any package to use it.

## Contents

- [1. Clone or download](#1-clone-or-download)
- [2. Create your project PRD](#2-create-your-project-prd)
- [3. Select a project profile](#3-select-a-project-profile)
- [4. Complete WHY and SCOPE](#4-complete-why-and-scope)
- [5. Define WHAT](#5-define-what)
- [6. Design HOW](#6-design-how)
- [7. Build traceability](#7-build-traceability)
- [8. Review with an AI coding agent](#8-review-with-an-ai-coding-agent)
- [9. Obtain implementation approval](#9-obtain-implementation-approval)
- [Profile examples](#profile-examples)
- [Common mistakes](#common-mistakes)

## 1. Clone or Download

Clone with Git:

```bash
git clone <repository-url>
cd fullstack-vibe-coding-prd-template
```

Alternatively, download the repository archive from GitHub and extract it locally.

No dependency installation is required. Any command or technology mentioned inside a project PRD is a proposal until your project approves it.

## 2. Create Your Project PRD

Copy the master file instead of editing the repository template in place:

```bash
cp templates/MASTER_FULLSTACK_PRD_TEMPLATE.md docs/MY_PROJECT_PRD.md
```

Choose a location and filename appropriate for your own repository. Set the new document status to `DRAFT`.

Do not copy the worked example and merely rename its entities. Use the example to understand relationships; use your verified project facts to fill the master.

## 3. Select a Project Profile

Choose one profile before deciding how much detail to add.

### Small/MVP

Select this profile when:

- the scope is intentionally narrow;
- there are few roles and routes;
- persistent data, authentication, or integrations may not be needed;
- a compact critical-path traceability matrix is sufficient.

Keep conditional sections visible. If a backend or database is not needed, write `N/A — [RATIONALE]` rather than inventing one.

### Standard Full-Stack

Select this profile when the project has:

- a real frontend;
- a backend API;
- persistent data;
- authentication, authorization, or equivalent trust boundaries;
- several connected UI, service, API, and data contracts.

The [Research Task Tracker example](../examples/RESEARCH_TASK_TRACKER_PRD.md) uses this profile.

### Complex Application

Select this profile when the project introduces:

- multiple roles or data scopes;
- external integrations;
- async or long-running processing;
- sensitive data or regulatory requirements;
- migration, recovery, high availability, or capacity concerns;
- extensive alternate and failure flows.

When uncertain, start with the smaller profile and record unresolved complexity as `DECISION REQUIRED`.

## 4. Complete WHY and SCOPE

Fill Sections 1–8 first.

### Establish project identity

Record:

- project name;
- one-sentence description;
- owners and current status;
- selected profile and delivery level.

### Define the problem

Separate verified problems from solution ideas. A statement such as “users manually copy records between spreadsheets” is a problem claim. “Build a dashboard” is a proposed solution.

Label assumptions and unsupported evidence as `TBD`.

### Define goals, scope, and non-goals

Create explicit IDs such as:

- `NEED-001` for a user need;
- `GOAL-001` for a product outcome;
- `SCOPE-001` for an included capability;
- `NON-GOAL-001` for an excluded capability.

Record decisions that block dependent work as `DECISION REQUIRED` in a `DEC-*` record.

### Complete the first review

Before detailed design, review WHY and SCOPE with the relevant human owner. The template calls this `GATE-01`.

## 5. Define WHAT

Complete Sections 9–12.

### Information architecture

List the actual page hierarchy and route registry. Avoid adding routes simply because a familiar application usually has them.

### Core features

Define each feature with a stable ID such as `CF-001`. Connect it to:

- a user need;
- a goal;
- a role;
- a flow;
- atomic functional requirements;
- pages/routes;
- API and data dependencies when applicable;
- acceptance criteria.

### Functional requirements

Write small, verifiable behaviors:

```text
FR-001 — The system MUST return only records authorized for the current role and resource scope.
```

Avoid combining unrelated behavior into one requirement.

### Pages and states

For every data-driven page, consider applicable states:

- loading;
- empty;
- success;
- validation error;
- permission denied;
- server/network error.

## 6. Design HOW

Complete Sections 13–22 at the depth required by your profile.

### ASCII wireframes

Use ASCII wireframes to show hierarchy and controls without implying pixel-perfect visual design. Each active wireframe should reference its `WF-*`, `PAGE-*`, `ROUTE-*`, and `CF-*` records.

### Mermaid diagrams

Use Mermaid only when a diagram removes ambiguity. Add metadata that identifies the canonical flows, features, pages, routes, services, APIs, data, security requirements, and decisions represented.

A diagram illustrates requirements; it does not silently create them.

### Technology decisions

The default frontend preference is React JS + Vite + Tailwind CSS. React Router and Lucide React are conditional. TanStack Query, React Hook Form, and Zod are recommendations only when their project value is documented.

Select backend, database, authentication, and infrastructure based on project requirements. Use `TBD`, `DECISION REQUIRED`, or `N/A — [RATIONALE]` when the choice is not ready.

### UX and architecture iteration

UX/design and technical architecture can develop iteratively. If a technical constraint changes an approved user flow, update the affected canonical records and review both sides again.

The template calls the UX review `GATE-02` and the architecture/API/data/security review `GATE-03`.

## 7. Build Traceability

Connect the project layers:

```text
User Need
  -> Goal
  -> Core Feature
  -> Functional Requirement / Business Rule
  -> Page / Route
  -> API
  -> Data Model
  -> NFR / Security Control
  -> Acceptance Criterion
  -> Test / Evidence
```

Use explicit IDs. Do not rely on labels such as “the API above.”

For critical features, use Given/When/Then acceptance criteria. Keep each test `PROPOSED` or `NOT RUN` until actual evidence exists.

A Small/MVP project may use a compact matrix for critical paths. Standard and Complex projects should cover the complete active scope.

## 8. Review with an AI Coding Agent

An AI coding agent can help identify:

- unresolved placeholders;
- contradictory requirements;
- orphan routes, APIs, or entities;
- missing error and permission states;
- broken traceability;
- architecture risks;
- proposed tests that do not verify acceptance criteria.

The agent should read the PRD first and propose corrections before implementation. It must not treat receipt of the document as coding permission.

See the [AI Agent Guide](ai-agent-guide.md) for reusable prompts.

## 9. Obtain Implementation Approval

Prepare a bounded implementation plan that states:

- approved features and requirements;
- files or components expected to change;
- dependency decisions;
- database/migration boundaries;
- verification commands;
- rollback or stop approach;
- explicit exclusions.

Obtain `GATE-04` before application coding begins.

Implementation should proceed incrementally, with actual test evidence attached to the relevant `TEST-*` and acceptance records. Production release or deployment requires a separate, target-specific `GATE-05`.

## Profile Examples

### Small/MVP example

A static event-information site might use:

- one public role;
- three routes;
- no authentication;
- no backend or database;
- three ASCII wireframes;
- one navigation flow;
- client-only acceptance criteria.

Backend and persistence sections remain `N/A — [RATIONALE]`.

### Standard Full-Stack example

A task tracker might use:

- public login plus authenticated pages;
- role-scoped data;
- a backend API and relational database;
- authentication and authorization contracts;
- API/data traceability;
- integration and E2E acceptance scenarios.

See the [complete worked example](../examples/RESEARCH_TASK_TRACKER_PRD.md).

### Complex Application example

A regulated multi-organization platform might additionally require:

- tenant isolation;
- delegated administration;
- audit retention;
- external identity and data integrations;
- queues and background processing;
- recovery targets;
- migration and rollback plans;
- threat/compliance review;
- full bidirectional traceability.

These are examples of depth—not features to add automatically.

## Common Mistakes

- Starting with technology before confirming the problem.
- Treating a wireframe as the only requirement.
- Inventing endpoints from UI controls.
- Treating hidden UI controls as authorization.
- Marking proposed tests as passed.
- Describing mock data or authentication as production-ready.
- Removing conditional sections without a rationale.
- Using an approval label without recording the approved version and scope.
- Assuming implementation approval also authorizes deployment.

## Next Reading

- [Master Template](../templates/MASTER_FULLSTACK_PRD_TEMPLATE.md)
- [Worked Example](../examples/RESEARCH_TASK_TRACKER_PRD.md)
- [PRD Workflow](prd-workflow.md)
- [AI Agent Guide](ai-agent-guide.md)
- [v0.2 Review Notes](review-notes-v0.2.md)
