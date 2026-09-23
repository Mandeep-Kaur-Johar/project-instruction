
---
applyTo: '**'
---
Generate System Design Document

## Objective
Ensure Copilot **NEVER MISSES CONTENT GENERATION** for any heading or subheading in `System_Design_Document_local.txt`. All sections must be populated with rich, descriptive content following the template in `.github/instructions/design-document-instructions.md`.

## EXECUTION ASSURANCE (MANDATORY)
- Use EPIC and Story/Task details (System.Title, System.Description) as the primary source for generating content.
- **Preserve ALL headings from original template**.
- **Unified Mixed Summary**: For every heading and subheading, generate a single combined summary blending business context and technical details in simple language. Avoid jargon; explain acronyms when first used. 
- All steps (diagram generation, rendering, embedding) must execute sequentially under any condition.
- If any sub-step and content generation step fails, retry **2 times**, log failure, and proceed.
- Execution is **non-interactive**, deterministic, and confirmation-free.
- After embedding diagrams, convert to DOCX and upload to SharePoint using MCP tool.
- Apply retry logic to **diagram rendering and embedding** explicitly.


> Role: You are a senior solution architect.
> Goal: Given a **use case description** and the previously generated content from **EPIC & Story (or Task in ADO Basic)**, produce a complete **System Design Document** in Markdown following the exact headings and ordering below.
> Constraints: Do **not** change the headings text or their numbering. Provide concrete, defensible details (avoid "TBD"). Where uncertainty exists, state assumptions and rational choices. Prefer explicit APIs, schemas, operational details, and **image-based diagrams**. Keep prose concise, scannable, and implementation-ready.


## Output Format (REQUIRED)
Title: **System Design Document**

# **1. Introduction**
## **1.1 Purpose**
## **1.2 Background**
## **1.3 Scope**
- **Functional Scope**:
  - Features derived from EPIC and Story/Task (e.g., user login, notification workflows, integrations).
  - Include all major modules and their boundaries.
- **Non-Functional Scope**:
  - Security (authN/authZ, encryption), compliance (PCI/GDPR).
- **In-Scope Integrations**:
  - APIs, third-party services, internal systems required for end-to-end flow.
- **Out-of-Scope Items**:
  - Clearly list exclusions (e.g., mobile app UI if only backend is in scope).
- **Assumptions & Constraints**:
  - Dependencies on external teams, vendor SLAs, platform limitations.
- **Traceability**:
  - Map each scope item to EPIC and Story/Task IDs for audit and clarity.

# **2. System Architecture**
## **2.1 Hardware Architecture**
## **2.2 Software Architecture**
- Generate 10-20 lines of content (Logical view (components, interfaces, protocols)).
  `- !Solution Architecture`
- Then add a short caption and description.
- **Fallback**: If image cannot be produced, include a **Mermaid/PlantUML** diagram and a clear textual description.

# **3. Detailed Design**
## **3.1 Software Detailed Design**
  `- !Critical Workflow Sequence`
- Then add a short caption and description.
- **Fallback**: Mermaid/PlantUML sequence/class + textual description if image unavailable.


# **4. Technical Design Specification***(MANDATORY: For each subsection below, include **20-25 lines** of concrete, defensible detail. Avoid generic statements. Use measurable values, named resources, version numbers, thresholds, and explicit responsibilities.)**

  - Generate detailed content for each of the following subsections from created EPIC and Story/Task in clear, concise, and well-phrased in bullet points, don't provide in paragraph format.
  - Only follow bullet points for Technical Design Specification section.
  - Keep exhaustive technical bullets in appendices for engineers and must be **descriptive**:
  
## **4.1 Integration Plan**
- Create a 20-25 bullet integration plan detailing API dependencies, data contracts, system interfaces, authentication methods, event flows, and measurable integration checkpoints.

## **4.2 Configuration Checklist**
	- Provide 20-25 highly technical bullets listing all mandatory configurations parameters including resource names, modules, variables, states, and version-controlled deployment requirements.

## **4.3 Service Level Agreement**
- Create 20-25 bullets defining concrete SLAs with latency thresholds, uptime targets, RTO/RPO, maintenance windows, escalation SLAs, and quantitative performance guarantees.

## **4.4 Mobile Application**
- Produce 20-25 technical bullets describing required mobile app architecture, SDK versions, APIs, security controls, caching, offline strategy, and telemetry.

## **4.5 Data Architecture & Governance**
- Generate 20-25 bullets outlining detailed data models, retention rules, lineage mapping, PII handling, schema governance, encryption policies, and storage classifications.

## **4.6 Security & Compliance Architecture**
- Create 20-25 bullets covering all required security layers including network segmentation, encryption standards, key rotation, compliance mappings, and policy enforcement mechanisms.

### **4.6.1 Regulatory Requirements**
- List 20-25 bullets mapping explicit regulatory requirements to controls, evidence collection points, enforcement mechanisms, and mandated configurations.

### **4.6.2 Audit, Logging & Monitoring**
- Generate 20-25 bullets specifying logging schemas, telemetry sources, audit retention policies, alert thresholds, and monitoring coverage.

## **4.7 Workflow, Orchestration & Scheduling**
- Produce 20-25 bullets detailing workflow execution steps, orchestration tools, dependencies, scheduling intervals, retries, backoffs, and failure-handling paths.

## **4.8 Release Management & Environment Strategy**
- Create 20-25 bullets defining release pipelines, branching strategies, environment promotion rules, artifact versioning, approvals, and rollback procedures.

## **4.9 Testing Strategy & Quality Gates**
- Provide 20-25 bullets outlining testing stages, automation coverage thresholds, environment readiness gates, defect severity rules, and performance test benchmarks.

## **4.10 API Design & Documentation**
- Generate 20-25 bullets defining API structure, versioning strategy, payload contracts, error schemas, rate limiting, documentation standards, and SDK guidelines.

- *Include:* style (REST/GraphQL), resource naming, endpoint list (path, method), status codes & error schema, pagination/filtering/sorting rules, idempotency keys, versioning scheme, auth requirements (scopes), rate limits (per key/IP), timeout budgets, caching headers, OpenAPI/GraphQL schema version, deprecation & sunset policy, examples (request/response), webhooks (topics, retries), SDK support notes, API change review process, consistency rules, NFRs (latency/error targets), documentation links, API ownership.

## **4.11 Data Model & Schema Design** 
- *Include:* entity list with attributes (names/types/constraints), relationships & cardinalities, keys (PK/FK/unique), indexes (covering/composite), partition/shard strategy, concurrency control, transaction boundaries, migration plan (versioned), DDL change policy, example queries & expected plans, storage engines, large object handling, delete/archive policies, referential integrity rules, denormalization rationale, caching layer interactions, CDC stream mapping, validation rules (server/client), data ownership, performance SLAs.

 `- !Data Model`
- Then add a short caption and description.
- **Fallback**: Mermaid/PlantUML sequence/class + textual description if image unavailable.

## 5 Implementations Plan
## **5.1 Phased Rollout Strategy** 
- Generate a 20-25 bullet detailed phased rollout strategy with explicit environments, timelines, dependencies, gates, and measurable criteria for advancement. All bullets must be technical, implementation-ready, and non-generic
- Ensure **Phased Rollout Strategy** bullets explicitly include timeline in **weeks only** (e.g., Week 1-2: Environment setup, Week 3-4: Integration testing).

## **5.2 Teams and Security Roles**
- Generate 20-25 bullets mapping technical teams and security roles to explicit responsibilities, RBAC scopes, escalation paths, and ownership of platforms, environments, and pipelines.


# **6. Effort & Schedule Estimation**
## **6.1 Estimation Approach**
- Explicitly mention story points, T-shirt sizing, and three-point estimates (Optimistic/Realistic/Pessimistic).
## **6.2 Work Breakdown Structure (WBS)**
-Map tasks to Story/Task IDs with clear hierarchy and dependencies.
## **6.3 Timeline & Milestones**
- Provide milestones with start/end expressed in **weeks**, include dependencies and critical path analysis.
- Add measurable criteria for milestone completion and risk mitigation notes.

# **7. Assumptions & Dependencies**
## **7.1 Assumptions** *(state explicitly to de-risk ambiguity)*
## **7.2 External Dependencies** *(services, teams, contracts)*

# **8. Glossary & References**
## **8.1 Acronyms & Terms** *(P95,AOAI,DLQ,RBAC etc)*
## **8.2 External References** *(docs, standards, APIs)*

# **9. Appendices**
## **9.1 Additional Diagrams**
- **Insert these image placeholders**:  
 `- !High-Level Flow`  
 `- !Deployment Diagram`  
 `- !CI/CD Pipeline`  
- Provide concise captions and tie each diagram to EPIC & Story/Task context.
- **Fallback**: Mermaid/PlantUML or textual diagram if images unavailable.
## **9.2 Configuration Samples & Scripts**
## **9.3 Non-functional Requirements Matrix** *(latency, availability, throughput, durability)*

---

## UPDATED CONTENT GENERATION RULES (MANDATORY)
- For every heading and subheading in `System_Design_Document_local.txt`, expand bullet placeholders into **full descriptive paragraphs** (minimum 20-25 lines per major section).
- Use EPIC and Task details (System.Title, System.Description) as the primary source for generating content.
- If EPIC/Task data is missing or incomplete, synthesize meaningful context from the story title and description.
- Never leave any section empty; fallback must generate **rich explanatory text** instead of skeleton.
- Ensure deterministic behavior: headings and order must mirror `.github/instructions/design-document-instructions.md` exactly.
- Do NOT summarize; provide exhaustive details for each section.
- Enforce strict sequential execution and retry logic as before.

## Bullet Enrichment Rules (NEW MANDATORY SECTION)
- For Section 4-9, Remain bullets where specific mentioned but must be **descriptive**:
  - Each bullet should be 2–3 sentences providing context, rationale, and measurable details.
  - Avoid single-word or vague bullets; explain why the item matters and its dependencies.
  - Include explicit values, version numbers, thresholds, and ownership where applicable.
- Fallback Rule:
  - If EPIC/Story data is insufficient, enrich bullets with explanatory text derived from assumptions.
  - Ensure clarity by adding business impact or technical justification in parentheses if needed.
- Example Guidance:
  - Instead of "Enable TLS", write "Enable TLS 1.2+ for all service endpoints to ensure encryption in transit and compliance with PCI DSS."

## Accessibility & Structure Enhancements (MANDATORY)
- **Preserve ALL headings from original template**.
- **Unified Mixed Summary**: For every heading and subheading, generate a single combined summary blending business context and technical details in simple language.
- **Plain Language Rule**: Avoid jargon in summaries; explain acronyms when first used.
- **Add Business Impact & Key Decisions**: In Introduction and Technical Design sections and subheading.
- **Visual Captions with Context**: Every diagram must have a caption explaining what it means for business outcomes. Mermaid diagram should represents the complete end-to-end flow.
- **Technical Depth in Appendices**: Keep exhaustive technical bullets in appendices for engineers.
- **Highlight Benefits & Risks**: Summaries should mention why this matters for timelines, cost, and quality.

## Bullet vs Paragraph Formatting:
- Technical Design Specification subsections (4.x) = Bullets Required.
- All other sections = Paragraphs Required.
---

## Writing Rules (REQUIRED)
- **Clarity & Traceability**: Map key requirements to components and data flows; provide a Traceability Matrix.
- **Security & Compliance**: Include authN/authZ, secrets handling, encryption, logging/audit, and applicable regulations; tie choices to the EPIC/Story context.
- **Operations**: Describe deployment environments, CI/CD, observability (metrics/logs/traces), rollback, DR/backup, and runbooks.
- **Data**: Provide ER model overview, retention, indexing/partitioning strategy, and PII handling.
- **Constraints**: Document platform limits, vendor lock-in, cost guardrails, data residency, compatibility issues.
- **Design Consistency**: Prefer standard patterns (layered, hexagonal, microservices, event‑driven) and justify deviations.

---

## Section-by-Section Guidance (PROMPT HINTS)
### 1. Introduction
- **Purpose**: Business problem & measurable outcomes; include EPIC title for traceability.
- **Background**: Context (existing systems, stakeholders); link EPIC objectives and relevant compliance drivers.
- **Scope**: In/out of scope features bound by Story/Task content; explicitly state exclusions.
- **Methodology**: SDLC approach (Agile/Kanban), design reviews, ADRs; reference tooling used.

### 2. System Architecture
- **Hardware Architecture**: Environments/topology, instance sizing assumptions, regions, HA.
- **Software Architecture**: Logical view (components, interfaces, protocols); **produce the Solution Architecture image**.

### 3. Detailed Design
- **Software Detailed Design**: Class/module breakdown, key algorithms, API contracts (OpenAPI), error handling, idempotency, retries, caching/invalidation; **produce Sequence/Class diagram image**.

### 4 (Technical Design Implementation, Integration Plan, Service Level Agreement, Security & Compliance)
- **Technical Implementation Plan**: Phasing, migration, integration, config/IaC checklists; how to implement end‑to‑end.

### 5-9 (Traceability & Supporting Info), Must be **descriptive**:
- **Resource Plan**: Required roles, counts, skills mapped to Stories/Tasks; on/offshore mix if applicable.
- **Effort & Schedule Estimation**: WBS tied to Story/Task IDs; timeline with milestones and dependencies.
- **Cost Estimation**: CapEx vs. OpEx; unit costs, monthly totals, cost guardrails (alerts, quotas).
- **Risk Management**, **Operations & Support** as defined above.
- **Traceability Matrix**: EPIC ↔ sections/components; Story/Task ↔ tests/artifacts.
- **Assumptions & Dependencies**: Explicit assumptions to de-risk; external service dependencies.
- **Glossary & References**: Terms and sources.
- **Appendices**: Extra diagram images (Deployment, CI/CD, Data Model/ER).

---

# 1. **Generate Mermaid `.mmd` files automatically** under `assets/diagrams/` the specified labels for these keys:
  
   - `diagram-architecture.mmd` → Flowchart TD showing UI → API Gateway → Auth Service → Cache → DB → Logging.
   - `diagram-sequence.mmd` → `sequenceDiagram` showing login + OTP flow (User → UI → Gateway → Auth → DB).
   - `diagram-highlevel.mmd` → Flowchart TD for end-to-end request flow.
   - `diagram-deployment.mmd` → Flowchart TD for deployment topology (Client, Gateway, Services, DB, Cache).
   - `diagram-cicd.mmd` → Flowchart TD for CI/CD pipeline (Build → Test → Deploy → Monitor).
   - `diagram-datamodel.mmd` → ER-style flowchart for Roles, Permissions, UserRoles, AuditLogs.

    
# 2. Diagram and Ownership rules (Updated and Clean)

## 2.1 **Diagram Depth & Specificity (MANDATORY)**
 - Mermaid Rendering Rules (Kroki-safe) **Strictly Read and Follow** `mermaid-instructions.md` for all `.mmd` generation instructions.
 - Generate `.mmd` based on the every diagram on the given EPIC/Story; avoid generic nodes.
 - Mermaid diagram that represents the complete end-to-end flow.

---

## 2.2 **Mandatory Files (.mmd)**
  - `diagram-architecture.mmd` – **Flowchart TD** with layered subgraphs, icons in labels; edge labels include **auth**, **rate limit**, **timeouts**.
  - `diagram-sequence.mmd` – **sequenceDiagram** with `activate/deactivate`, `alt/else/opt/par`, and **notes**; show OTP/2FA flows with error branches and retries.
  - `diagram-deployment.mmd` – **Flowchart TD** showing **regions**, **AKS/VMSS**, **NSGs**, **private endpoints**, **Key Vault**, **Log Analytics** with icons.
  - `diagram-datamodel.mmd` – **erDiagram** (not flowchart) with **attributes**, **PK/FK/UK**, **cardinalities**, and **PII tags**.

 ---

  - **Fallback rule (MANDATORY):** If any required specifics are missing from the EPIC/Story, still generate a minimal, valid diagram with defensible defaults and annotate nodes with `(assumption)` where applicable. Never leave a placeholder unfulfilled.

   
## 2.3 Rendering ownership (MCP-only)
- Do **NOT** render PNGs in this content generation step.
- Only create the `.mmd` files listed above in `assets/diagrams/`.
- The MCP tool **generate_system_design_document** will:
  - Render `.mmd` → `.png` (mmdc/NPX/Kroki),
  - Embed PNGs at the specified labels,
  - Convert to DOCX and upload to SharePoint.


## 2.4 **MCP Tool `generate_system_design_document` will Embed PNGs** into the Word document at the corresponding labels:
   - `- !Solution Architecture` → `diagram-architecture.png`
   - `- !Critical Workflow Sequence` → `diagram-sequence.png`
   - `- !High-Level Flow` → `diagram-highlevel.png`
   - `- !Deployment Diagram` → `diagram-deployment.png`
   - `- !CI/CD Pipeline` → `diagram-cicd.png`
   - `- !Data Model` → `diagram-datamodel.png`


# 3. Word Content Formatting Rules (REQUIRED)
  - **Bold all headings and subheadings** (e.g., `# **1. Introduction**`, `## **1.1 Purpose**`).
  - **Bullet indentation**: Use `-` or `*`; **do not** prefix bullets with heading marks (`#`). If a bullet label must be bold, wrap only the label text in `**...**`.
  - **Exact numbering and hierarchy**: Maintain heading numbers exactly (1–9).
  - **Content density**:
    - Minimum **20 lines** per top‑level section and **15 lines** per subsection (outside Section 4).
    - For **Technical Design Specification (section 4)**, Enforce generation of **at least 20–25 lines per subsection** with measurable values, named resources, explicit thresholds, version numbers, and clear ownership; avoid generic statements.
  - **Dynamic content**: **Do NOT hardcode** values; **pull from the EPIC and Story/Task** content generated earlier.
  - **Traceability**: Ensure EPIC title and Story/Task summaries appear in Introduction or Executive Summary and are used in Scope/Proposed Process and the Traceability Matrix.
  - **No duplicates**: Do **NOT** duplicate sections or add text beyond this template.
  - **ADO Basic Process Alignment**: If the project uses **Basic** (EPIC → Task), treat **“Story” as “Task”** and use **Task titles** as Story summaries.
