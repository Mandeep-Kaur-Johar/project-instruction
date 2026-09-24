---
applyTo: '**'
---

# Generate System Design Document (General SDLC Template)

## Objective
This file is a **reusable master template and instruction set** for generating a System Design Document (SDD) from any source requirement input — an EPIC, a user story, a task, a feature request, a use-case brief, or a stakeholder write-up. It is intended as the **sample/reference** for producing any SDLC design document, regardless of the source project-management tool (Azure DevOps, Jira, Notion, plain text brief, etc.).

Wherever this template says **"Source Requirement"**, substitute whatever unit of work is actually driving the document (Epic, Story, Task, Feature, Use Case). Wherever it says **"Source ID"**, substitute the corresponding identifier from whatever tracking system is in use.

## Execution Principles (MANDATORY)
- Mention the content, which is important keep it short yet meaningful. Do not over explain or explain too much. Keep short lines, do not mention paragraphs.
- Never leave a heading or subheading without content. Every section must be populated with rich, descriptive, implementation-ready content.
- Use the Source Requirement's title and description as the primary input for content generation. If details are incomplete, synthesize reasonable content and clearly label it as an **assumption**.
- Preserve **all headings exactly as numbered** below — do not rename, reorder, merge, or omit them.
- Avoid "TBD" or empty placeholders. Where uncertainty exists, state the assumption and the rationale behind the choice made.
- Blend business context and technical detail into simple, plain language. Expand any acronym on first use.
- Diagrams should be described as image placeholders with a fallback to Mermaid/PlantUML plus a text description when an image cannot be produced.
- Treat this as a deterministic, non-interactive template: the same inputs should produce the same structure every time.

---

## Output Format (REQUIRED)

Title: **System Design Document**

# **1. Introduction**
## **1.1 Purpose**
- Provide the business problem in 2 lines.

## **1.2 Scope**
- **Functional Scope**: Features derived from the Source Requirement in max 2 lines.
- **Non-Functional Scope**: Security, compliance.
- **In-Scope Integrations**: APIs, third-party services, internal systems required for the end-to-end flow.
- **Out-of-Scope Items**: Explicit exclusions (e.g., mobile UI if only backend is in scope).
- **Assumptions & Constraints**: Dependencies on external teams, vendor SLAs, platform limitations.

## **1.3 Methodology**
- SDLC approach used (Agile, Kanban, Waterfall, hybrid), design review process, architecture decision records (ADRs), and tooling used to produce this document.

# **2. System Architecture**

## **2.1 Software Architecture**
- 5–10 lines describing the logical view: components, interfaces, protocols.
- `- !Solution Architecture`
- Add a short caption and description explaining the diagram's business meaning.
- **Fallback**: If an image cannot be produced, include a Mermaid/PlantUML diagram plus a clear textual description.

# **3. Detailed Design**
## **3.1 Software Detailed Design**
- Class/module breakdown, key algorithms, API contracts, error handling, idempotency, retries, caching/invalidation strategy.
- `- !Critical Workflow Sequence`
- Add a short caption and description in 2 lines.
- **Fallback**: Mermaid/PlantUML sequence or class diagram plus textual description if an image is unavailable.

# **4. Technical Design Specification**
*(MANDATORY: fFor each subsection below, include 3–5 concise bullets, Focus on implementation-critical information only. — measurable values, named resources, version numbers, thresholds, and explicit ownership. Bullet points only in this section; no paragraphs.)*

## **4.1 Integration Plan**
- 5 bullets covering API dependencies, data contracts, system interfaces, authentication methods, event flows, and measurable integration checkpoints.

## **4.2 Configuration Checklist**
- 5 bullets listing mandatory configuration parameters: resource names, modules, variables, states, and version-controlled deployment requirements.

## **4.3 Service Level Agreement**
- 5 bullets defining concrete SLAs: latency thresholds, uptime targets, RTO/RPO, maintenance windows, escalation SLAs, quantitative performance guarantees.

## **4.4 Security & Compliance Architecture**
- 5 bullets covering network segmentation, encryption standards, key rotation, compliance mappings, and policy enforcement mechanisms.

## **4.5 Workflow, Orchestration & Scheduling**
- 5 bullets on workflow execution steps, orchestration tools, dependencies, scheduling intervals, retries, backoffs, and failure-handling paths.

## **4.6 Release Management & Environment Strategy**
- 5 bullets defining release pipelines, branching strategy, environment promotion rules, artifact versioning, approvals, and rollback procedures.

## **4.7 Testing Strategy & Quality Gates**
- 5 bullets outlining testing stages, automation coverage thresholds, environment readiness gates, defect severity rules, and performance benchmarks.


# **5. Implementation Plan**
## **5.1 Phased Rollout Strategy**
- 5-10 bullets, technical and implementation-ready (not generic), covering environments, timelines, dependencies, gates, and measurable advancement criteria.
- Express all timelines in **weeks** (e.g., "Week 1–2: environment setup", "Week 3–4: integration testing").
## **5.2 Teams and Security Roles**
- 5-10 bullets mapping teams and security roles to responsibilities, RBAC scopes, escalation paths, and ownership of platforms, environments, and pipelines.

# **6. Effort & Schedule Estimation**
## **6.1 Estimation Approach**
- Explicitly mention story points, T-shirt sizing, and three-point estimates (Optimistic/Realistic/Pessimistic).

## **6.2 Timeline & Milestones**
- 5 bullets points Milestones with start/end in weeks, dependencies, and critical-path analysis.

# **7. Assumptions & Dependencies**
## **7.1 Assumptions**
- State explicitly to de-risk ambiguity.
## **7.2 External Dependencies**
- Services, teams, contracts, vendor SLAs.


# **8. Appendices**
## **8.1 Additional Diagrams**
- Insert image placeholders:
  - `- !High-Level Flow`
  - `- !Deployment Diagram`
  - `- !CI/CD Pipeline`
- Provide concise captions tying each diagram back to the Source Requirement context.
- **Fallback**: Mermaid/PlantUML or textual diagram if images are unavailable.



---

## Content Generation Rules (MANDATORY)

- Expand every section with sufficient information to support implementation and review.
 Target:
- 3–5 lines per subsection
- 5–8 lines per major section and Avoid repetition..
- Use the Source Requirement's title/description as the primary source; synthesize meaningful context from it if details are missing.
- Never leave a section empty — generate 1 liner text.
- Headings and order must mirror this template exactly.
-Provide concise, implementation-ready detail.
-Avoid unnecessary repetition.
-Prefer short, actionable content over large narrative sections.

## Bullet Enrichment Rules
- In Sections 4–9, keep content as bullets where specified, but make each bullet descriptive:
  - 2–3 sentences providing context, rationale, and measurable detail.
  - Avoid single-word or vague bullets; explain why the item matters and its dependencies.
  - Include explicit values, version numbers, thresholds, and ownership where applicable.
- If source data is insufficient, enrich with explanatory text derived from stated assumptions, and note business impact or technical justification in parentheses where useful.
- Example: instead of "Enable TLS," write "Enable TLS 1.2+ for all service endpoints to ensure encryption in transit and compliance with PCI DSS."

## Accessibility & Structure Enhancements
- Preserve all headings from this template.
- For every heading/subheading, produce one unified summary blending business context and technical detail in plain language; explain acronyms on first use.
- Add "Business Impact & Key Decisions" callouts in the Introduction and Technical Design sections.
- Every diagram needs a caption explaining its business meaning; Mermaid diagrams should represent the complete end-to-end flow.
- Keep exhaustive technical bullets in the Appendices for engineers.
- Summaries should note why each item matters for timelines, cost, and quality.

## Bullet vs. Paragraph Formatting
- Section 4 (all Technical Design Specification subsections): bullets required.
- All other sections: paragraphs required.

## Writing Rules
- **Clarity & Traceability**: Map key requirements to components and data flows; include a Traceability Matrix.
- **Security & Compliance**: Cover authN/authZ, secrets handling, encryption, logging/audit, and applicable regulations tied to the Source Requirement.
- **Operations**: Describe deployment environments, CI/CD, observability (metrics/logs/traces), rollback, DR/backup, and runbooks.
- **Data**: Provide an ER model overview, retention policy, indexing/partitioning strategy, and PII handling.
- **Constraints**: Document platform limits, vendor lock-in, cost guardrails, data residency, compatibility issues.
- **Design Consistency**: Prefer standard patterns (layered, hexagonal, microservices, event-driven) and justify any deviation.

---

## Diagram Generation

### 1. Required Diagram Source Files
Generate Mermaid `.mmd` files under `assets/diagrams/`:
- `diagram-architecture.mmd` → Flowchart TD: UI → API Gateway → Auth Service → Cache → DB → Logging.
- `diagram-sequence.mmd` → sequenceDiagram: critical workflow (e.g., login + OTP: User → UI → Gateway → Auth → DB).
- `diagram-highlevel.mmd` → Flowchart TD: end-to-end request flow.
- `diagram-deployment.mmd` → Flowchart TD: deployment topology (client, gateway, services, DB, cache).
- `diagram-cicd.mmd` → Flowchart TD: CI/CD pipeline (build → test → deploy → monitor).
- `diagram-datamodel.mmd` → ER-style diagram for core entities and their relationships.

### 2. Diagram Depth & Ownership
- Base every diagram on the actual Source Requirement — avoid generic, unlabeled nodes.
- Each diagram should represent the complete end-to-end flow it is meant to illustrate.
- Required specificity per diagram:
  - **Architecture**: layered subgraphs; edge labels include auth, rate limits, timeouts.
  - **Sequence**: activate/deactivate, alt/else/opt/par blocks, notes; show error branches and retries.
  - **Deployment**: regions, compute (e.g., AKS/VMSS), network security groups, private endpoints, secrets store, log/monitoring destination.
  - **Data Model**: use an ER diagram (not a flowchart) with attributes, PK/FK/UK markers, cardinalities, and PII tags.
- **Fallback rule**: If specifics are missing from the Source Requirement, still generate a minimal, valid diagram with defensible defaults, annotating assumed nodes with `(assumption)`. Never leave a diagram placeholder unfulfilled.

### 3. Rendering & Embedding
- Diagram source generation (`.mmd` files) and diagram rendering/embedding (`.mmd` → `.png` → embedded in the document) can be separated: author the `.mmd` files first, then render and embed as a later step (via any diagram renderer or document-generation tool available in the environment).
- Map rendered diagrams to their placeholders:
  - `- !Solution Architecture` → `diagram-architecture.png`
  - `- !Critical Workflow Sequence` → `diagram-sequence.png`
  - `- !High-Level Flow` → `diagram-highlevel.png`
  - `- !Deployment Diagram` → `diagram-deployment.png`
  - `- !CI/CD Pipeline` → `diagram-cicd.png`
  - `- !Data Model` → `diagram-datamodel.png`

---

## Document Formatting Rules
- Bold all headings and subheadings (e.g., `# **1. Introduction**`, `## **1.1 Purpose**`).
- Use `-` or `*` for bullets; never prefix a bullet with a heading mark (`#`). If a bullet label needs emphasis, bold only the label text.
- Preserve exact numbering and hierarchy (Sections 1–9).
- Content density: minimum 20 lines per top-level section and 15 lines per subsection outside Section 4; Section 4 subsections need 20–25 lines each with measurable values, named resources, thresholds, versions, and clear ownership.
- Pull all values dynamically from the Source Requirement — do not hardcode figures.
- Ensure the Source Requirement's title and summary appear in the Introduction/Executive Summary and are reflected in Scope and the Traceability Matrix.
- Do not duplicate sections or add content beyond this template's structure.
- If the source tracking system only has a single work-item level (e.g., Epic → Task, no separate "Story"), treat "Task" as "Story" throughout.

---

## Using This Template for Any SDLC Document
This structure and rule set generalizes beyond System Design Documents. To reuse it for another SDLC artifact (e.g., a Test Plan, Deployment Runbook, or Architecture Decision Record):
1. Keep the numbered heading skeleton and formatting rules intact.
2. Swap Section 2–5 content for the artifact-specific technical detail required.
3. Keep Sections 1, 6–9 (Introduction, Estimation, Assumptions, Glossary, Appendices) as-is — they apply to virtually any SDLC document.
4. Retain the bullet-enrichment and diagram fallback rules so output quality stays consistent across document types.
