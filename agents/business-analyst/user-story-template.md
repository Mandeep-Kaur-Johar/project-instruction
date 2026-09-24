---
applyTo: '**'
---
# User Story Template

> **Instructions for use:** This file defines the standard structure every user story must follow. When generating a new user story, populate each section below using information gathered from the requester/context, or — if this story is being broken down from an Epic — from the parent Epic (see **Epic Template**). Do not omit sections — if information is unavailable, mark it `TBD` and add it to **Open Questions**. Keep field labels exactly as shown so downstream tooling can parse them consistently.

## EXECUTION ASSURANCE (MANDATORY)
- **Never skip or thin out Acceptance Criteria or Non-Functional Requirements.** These two sections are the most commonly dropped or under-filled and must always be fully populated, in the exact format specified below, regardless of how sparse the source input is.
- **If this story has a parent Epic**, pull directly from it rather than re-deriving content from scratch:
  - **Business Feature** ← the Epic's Title and ID.
  - **Acceptance Criteria** ← trace each AC back to at least one of the Epic's Success Criteria (SC1, SC2...).
  - **Non-Functional Requirements** ← start from the matching line(s) in the Epic's NFR Baseline, narrowed to what this specific story touches. Never leave an NFR field blank on the assumption "the Epic already covers it."
- If input is insufficient to write a concrete Acceptance Criterion or NFR, synthesize a defensible default based on the story's scenario and label it `(assumption)` — do not delete the field or leave it empty.
- Preserve all headings and field labels exactly as shown; do not rename, reorder, or merge sections.
- Execution is non-interactive and deterministic: given the same input, produce the same structure every time.
- After completing this story, add its ID/title/Success-Criteria mapping to the parent Epic's **Child Stories / Tasks** table.

---

## **User Story**
**Title:** [Short, action-oriented title summarizing the capability]
**As a [Persona/Role], I want [capability/action], so that [business benefit/outcome].**

---

### **Business Feature**
- **Name/Link:** [Feature name or link to feature/epic]
- **Product/Capability:** [Product area or capability this belongs to]
- **Parent Epic:** [Epic ID/Title — link to Epic Template instance, if applicable]
- **Derived from Success Criteria:** [Epic SC id(s) this story helps satisfy, e.g., "SC1, SC3" — leave `N/A` only if there is genuinely no parent Epic]

---

### **Story Expectations**
- **Business value & impact:** [Why this matters; expected business/user impact]
- **Scope boundaries (In/Out):**
  - **In:** [What is included in this story]
  - **Out:** [What is explicitly excluded]
- **Required outcomes:** [Concrete outcome(s) that define success]

---

### **Detailed Description**
- **Context & problem statement:** [Background and the problem being solved]
- **Key scenarios / flows:**
  - [Scenario/flow step 1]
  - [Scenario/flow step 2]
  - [Scenario/flow step 3]
- **Assumptions:**
  - [Assumption 1]
  - [Assumption 2]

---

### **Acceptance Criteria** *(MANDATORY — minimum 3 criteria, Given/When/Then format)*
> This section must never be left with fewer than 3 conditions, even for a small story. Cover at minimum: (1) the primary happy-path scenario, (2) one edge case or validation failure, (3) one negative/error scenario. Each criterion must be independently testable, and — if a parent Epic exists — traceable to one of its Success Criteria.

- **AC1 — [short label, e.g. "Successful submission"]** *(traces to: [Epic SC id, e.g. SC1])*
  **Given** [precondition],
  **When** [action/event],
  **Then** [expected outcome].

- **AC2 — [short label, e.g. "Validation error"]** *(traces to: [Epic SC id])*
  **Given** [precondition],
  **When** [action/event],
  **Then** [expected outcome].

- **AC3 — [short label, e.g. "System/negative case"]** *(traces to: [Epic SC id])*
  **Given** [precondition],
  **When** [action/event],
  **Then** [expected outcome].

- *(Add AC4, AC5, … for additional scenarios as needed — do not renumber existing ones.)*

---

### **Non-Functional Requirements (NFRs)** *(MANDATORY — every field below must have a concrete value or a stated `(assumption)`, never blank or "N/A" without justification)*
> If this story has a parent Epic, start each line from the Epic's NFR Baseline and narrow it to what this story actually touches.

- **Performance:** [Target response time / throughput, e.g., "P95 API latency ≤ 300ms under 500 RPS"]
- **Reliability/Availability:** [Uptime target / SLA, e.g., "99.9% monthly uptime; auto-retry on transient failure"]
- **Security/Privacy:** [AuthN/authZ model, encryption in transit/at rest, data classification, access control]
- **Usability/Accessibility:** [Accessibility standard, e.g., WCAG 2.1 AA; specific usability targets]
- **Observability/Logging:** [What is logged, log retention, metrics/traces emitted, alert thresholds]
- **Compliance:** [Applicable regulations, e.g., GDPR, HIPAA, PCI-DSS, or "Not applicable — no regulated data" if genuinely none]
- **Scalability/Capacity:** [Expected load, concurrency, data volume growth this story must support]

---

### **Dependencies**
- **Upstream:** [Systems/teams this story depends on]
- **Downstream:** [Systems/teams that depend on this story]
- **External vendors/APIs:** [Third-party services involved]

---

### **Constraints / Policies**
- **Technical constraints:** [Platform, architecture, or tooling limitations]
- **Organizational/process constraints:** [Policy, compliance, or process requirements]

---

### **Environments & Platforms**
- **Target environments:** [e.g., Dev, Test, Stage, Prod]
- **Platforms/browsers/devices:** [e.g., Web (Chrome, Edge), Mobile, Desktop]

---

### **Stakeholders**
- **Requester:** [Name/Role]
- **Business owner:** [Name/Role]
- **Technical owner:** [Name/Role]
- **QA/Validation owner:** [Name/Role]

---

### **Estimation & Priority**
- **Priority:** [P0/P1/P2/P3]
- **Estimate:** [Story Points / Time estimate]
- **Estimation approach:** [e.g., Story Points, T-shirt sizing, Hours]

---

### **Definition of Ready (DoR) Checklist**
- Clear problem statement
- Persona identified
- Parent Epic and Success Criteria mapping identified (if applicable)
- Dependencies identified
- Acceptance criteria drafted (≥3, Given/When/Then)
- NFRs captured (all fields addressed)
- Test strategy agreed
- Effort range estimated
- Risks noted

---

### **Definition of Done (DoD) Checklist**
- Code complete & peer reviewed
- Tests written & passing (unit/integration/e2e), mapped to Acceptance Criteria
- NFRs validated (performance/security/accessibility checks run)
- Security checks passed
- Documentation updated
- Feature flags/toggles handled
- Telemetry in place
- Deployed to target environment(s)
- Parent Epic's Child Stories/Tasks table updated with final status
- Stakeholder sign-off

---

### **Links & Traceability**
- **Parent Epic/Feature:** [Link or ID]
- **Related stories/tasks:** [Link(s) or ID(s)]
- **Design/Spec:** [Link, e.g., System Design Document]
- **Test cases:** [Link — ideally one test case per Acceptance Criterion]
- **Runbook/Operational docs:** [Link]

---

### **Risks & Mitigations**
- **Risk:** [Risk description] | **Mitigation:** [Mitigation approach]

---

### **Open Questions**
- Q1: [Unresolved question 1]
- Q2: [Unresolved question 2]

---

### **Labels/Tags**
- Agile: User Story
- Product area: [Area]
- Team: [Team name]
- Sprint/Iteration: [Sprint/Iteration identifier]

---

## Formatting Rules (REQUIRED)
- Bold all field labels exactly as shown (e.g., `**Title:**`, `**Given**`, `**When**`, `**Then**`).
- Acceptance Criteria must use the `AC1`, `AC2`, `AC3`... numbering with a short label and a Success-Criteria trace tag, followed by Given/When/Then on separate lines.
- NFR fields are a fixed checklist — do not drop a field even if the answer is "Not applicable"; state why briefly instead of omitting it.
- Do not duplicate sections or add content beyond this template's structure.
- If generating multiple stories from one Epic, keep NFR wording consistent across sibling stories unless a story genuinely has a different target, and keep each story's Success-Criteria trace tags accurate.
- If there is no parent Epic, set **Parent Epic** and all "traces to" tags to `N/A — standalone story` rather than deleting the fields.
